# ASPNETCore-WebAPI-CodigoNativo
Exemplo de código ASP.NET Core com WebAPI que invoca codigo nativo Win32

## Pré-Requisitos para operar esta prova de conceito.
. Visual Studio 2015 Update 3
. NET Core 1.0.1 Tooling for Visual Studio (testado com Preview 2) - https://www.microsoft.com/net/core#windowsvs2015
. Nuget Command Line Interface (Windows x86 Distribution) (testado com v3.5.0) - https://dist.nuget.org/index.html
. Conhecimentos de como gerar pacotes Nuget a partir de uma shared library .xproj ou csproj - Uso do comando utilitário DotNet Pack - https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-pack e http://stackoverflow.com/questions/39377602/how-to-add-c-library-in-a-net-core-project.
. Extensão SwashBuckle como um pacote Nuget (rodar o comando Install-Package Swashbuckle) - https://github.com/domaindrivendev/Swashbuckle. Esta extensão irá suportar a exportação de classes Web API em formato Swagger.
. Instalar o Postan (Desktop ou Chrome) para facilitar os testes REST
. Conhecimento de como fazer invocação de métodos nativos com PInvoke - https://msdn.microsoft.com/en-us/library/42b9ea93(v=vs.110).aspx
. Conhecimento básico de REST
. Conhecimento básico ASP.NET Web API
. Conhecimento básico de ASP.NET Core

## Passos para rodar
  . Abra a Solution no Visual Studio
  . Veja e modifique o seu código do projeto Biblioteca Reusável para invocar DLLs nativas Win32 (também pode ser feito com libs Unix ou Mac)
  . Dentro do projeto Biblioteca Reusavel rode o comando DotNet Pack para gerar a biblioteca reusável. Ele vai gerar um arquivo .nuspec que descreve a biblioteca em formato JSON, que é pre-requisito para ser importado por um projeto ASP.NET .NET Core
  . Pelo Nuget Package Manager, incluir o diretorio onde o arquivo .nuspec foi gerado no path do package manager. Dica: http://stackoverflow.com/questions/10240029/how-to-install-a-nuget-package-nupkg-file-locally
  . Referenciar a biblioteca Nuget gerada pelo Biblioteca Reusavel no projeto AplicacaoRest-InvocacaoCodigoNativo.
  . Rodar a aplicacação (como self-host application ou pelo IIS Express).
  . Testar as chamadas remotas
  
