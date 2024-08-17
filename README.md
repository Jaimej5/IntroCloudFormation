# IntroCloudFormation (.YAML)

## CLI
Para crear o actualizar stacks desde la línea de comandos con AWS CLI instalado (sin GUI), navega al directorio correspondiente y ejecuta los siguientes comandos: [DOCUMENTACION OFICIAL DE AMAZON]

```bash
aws cloudformation deploy --stack-name prueba-001-cli --template-file sencilla.yaml
aws cloudformation deploy --stack-name prueba-002-cli-parametros --template-file parameters.yaml --parameter-overrides KeyPairParameter=demo-keys AMIIdParameter=ami-0ae8f15ae66fe8cda VPCIdParameter=vpc-0054d7c1b2cf913fb
```

## Funciones
Entre otras funciones intrínsecas en las que mayormente se juega con los outputs.

```bash
aws cloudformation deploy --stack-name prueba-functions --template-file functions.yaml --parameter-overrides KeyPairParameter=demo-keys AMIIdParameter=ami-0ae8f15ae66fe8cda VPCIdParameter=vpc-0054d7c1b2cf913fb
```

## Make -> 07
Automatizar comandos: Accion - target

## Conditions >> Staging
Deploy
```bash
aws cloudformation deploy --stack-name staging-conditionals --template-file stack-conditionals.yaml --parameter-overrides AMIIdParameter=ami-0ae8f15ae66fe8cda KeyPairParameter=demo-keys VPCIdParameter=vpc-0054d7c1b2cf913fb Environment=staging
aws cloudformation deploy --stack-name prod-conditionals --template-file stack-conditionals.yaml --parameter-overrides AMIIdParameter=ami-0ae8f15ae66fe8cda KeyPairParameter=demo-keys VPCIdParameter=vpc-0054d7c1b2cf913fb Environment=prod
```

Delete
```bash
aws cloudformation delete-stack --stack-name staging-conditionals
aws cloudformation delete-stack --stack-name prod-conditionals
```

## User Data
Deploy
```bash
aws cloudformation deploy --stack-name staging-userdata --template-file stack-userdata.yaml --parameter-overrides AMIIdParameter=ami-04a81a99f5ec58529 KeyPairParameter=demo-keys VPCIdParameter=vpc-0054d7c1b2cf913fb Environment=staging
aws cloudformation deploy --stack-name prod-userdata --template-file stack-userdata.yaml --parameter-overrides AMIIdParameter=ami-04a81a99f5ec58529gir KeyPairParameter=demo-keys VPCIdParameter=vpc-0054d7c1b2cf913fb Environment=prod
```

Delete
```bash
aws cloudformation delete-stack --stack-name staging-userdata
aws cloudformation delete-stack --stack-name prod-userdata
```