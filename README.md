# Terraform Quickstart

### Provisionamento do cluster+Rancher
#### Requisitos:
- Terraform >=0.13.0

- Credenciais da Amazon (aws_secret_key, aws_access_key)

#### Passo a passo:

```
git clone https://github.com/rancher/quickstart

cd quickstart/aws

mv terraform.tfvars.example terraform.tfvars
```

Editar arquivo com as variáveis desejadas. Os exemplos para subir Rancher v2.5.9 está em [Terraform TFVars](https://github.com/gbrlins/terraform-rancher-quickstart/blob/main/terraform.tfvars)

```
terraform init

terraform apply --auto-approve
```

Nesse momento, o processo iniciará e após alguns minutos, teremos a url para acessar a interface do Rancher, tornando a interface acessível após reboot.

### Dentro do Rancher

Na interface inicial, ir em Settings e alterar os seguintes campos:
server-url

No cluster local, no projeto "System", alterar a seguintes informaćões:

Em "Load Balancing", editar o ingress atual substituindo o hostname atual pela općão "Specify a hostname to use". 
Colocar o hostname reservado no DNS nesse campo.
Na mesma página, na opcão "SSL/TLS Certificates" alterar o host para o mesmo alterado no passo anterior.
