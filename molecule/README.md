# Molecule Testing

## Installation

```bash
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.yml
```

# Execution

Ubuntu 24.04:
```bash
MOLECULE_DISTRO=ubuntu2404 molecule test --scenario-name stroke

MOLECULE_DISTRO=ubuntu2404 molecule test --scenario-name vici
```

Ubuntu 22.04:
```bash
MOLECULE_DISTRO=ubuntu2204 molecule test --scenario-name stroke

MOLECULE_DISTRO=ubuntu2204 molecule test --scenario-name vici
```
