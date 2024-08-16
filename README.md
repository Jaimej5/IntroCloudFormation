# IntroCloudFormation (.YAML)
Para crear o actualizar stacks desde la línea de comandos con AWS CLI instalado, navega al directorio correspondiente y ejecuta los siguientes comandos: [DOCUMENTACION OFICIAL DE AMAZON]

```bash
aws cloudformation deploy --stack-name prueba-001-cli --template-file sencilla.yaml
aws cloudformation deploy --stack-name prueba-002-cli-parametros --template-file parameters.yaml --parameter-overrides KeyPairParameter=demo-keys AMIIdParameter=ami-0ae8f15ae66fe8cda VPCIdParameter=vpc-0054d7c1b2cf913fb