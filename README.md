# Aria
Personal IaC with GitOps first

## Development
### Test
This will be used by CI/CD (check `.github/workflows/test-playbooks.yml`)
```bash
docker-compose up
```

### Development check
```
docker run -it --rm -h "ubuntu" $(docker build -f docker/ubuntu/dockerFile . 2>&1| tail -1 | awk '{print $3}') bash -c 'ansible-playbook -i inventory/hosts local.yml; bash -'
```

## Checklists
### Adding new machine
- [ ] Add new docker compose service to `docker-compose.yml` with new machine imitations