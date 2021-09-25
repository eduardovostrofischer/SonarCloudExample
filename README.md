# open_movie

Exemplo de como baixar e executar o sonarQube para Flutter

## Getting Started

Pré requisitos:
    Java 11, para o sonarQube server
    Java 9 ou 11 para o sonarscanner

Instalando Java
Baixe a versão do Java 11 para windows em https://jdk.java.net/11/
Instale o Java e ele criará uma pasta em C:/ProgramFiles/Java
Na barra start procure por editar variaveis de ambiente -> Propriedades do sistema -> Avançado -> Variáveis de ambiente
Crie uma nova variável do sistema chamada JAVA_HOME e como valor coloque C:\Program Files\Java\jdk-11.0.11
Abra o PATH e adicione um caminho %JAVA_HOME%/bin
Reinicie o computador


Instalar o Sonarqube
Fazer o donwload em https://www.sonarqube.org/
    Caso de o erro Unrecognized option: --add-exports=java.base/jdk.internal.ref=ALL-UNNAMED ou outro erro envolvendo não conseguir lançar a maquina jvm. Verifique que está utilizando a versão java certa. 
    rode 'java -version' , deve aparecer java version"11.x.x".
    Depois de baixado, execute bin/StartSonar.bat
    Abra http://localhost:9000/




Instalar o sonarscanner
https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/
Baixe o Zip do sonarscanner
Abra o powershell e execute ./sonar-scanner.bat
Adicione em sonar-scanner.properties os campos: sonar.login="login" sonar.password="password" ou sonar.login="token"
Se acusar falta de projectkey, adicione projectKey em sonar-scanner.properties
new token = newtoken = cdbc696f4fe525eff63c7236b4ab538c843d4d42
Se no sonarqube avisar que o main branch está vazio, adicione essas propriedades em sonar-scanner.properties
    sonar.sources=lib
    sonar.tests=test
    sonar.sourceEncoding=UTF-8
    sonar.projectBaseDir=../../..

Instalar o plugin
Plugin está em https://github.com/insideapp-oss/sonar-flutter
Fazer o download do binário em Releases
Adicionar no %SonarQubeFolder%/extensions/plugins
Executar

Se o flutter analyze indicar erros mas o SonarQube não indicar.
Adicione sonar.dart.analysis.useExistingOptions=false em sonar-scanner.properties

Integração com Github
http://localhost:9000/documentation/analysis/github-integration/
Após instalar o Sonarqube e executa-lo