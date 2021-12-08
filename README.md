# **GitLab-Runner **

Configuração e execução do GitLab Runner. 



### Requisitos

- Instalação do GitLab Runner

- Registro dos Runners

- Instalação do MAVEN

  

###  Instalação GitLab-Runner

1. Download do ***gitlab-runner.exe*** -  [*Git Runnes - Instalação*](https://docs.gitlab.com/runner/install/windows.html) e *[Git Runners - Configuração](https://docs.gitlab.com/runner/register/index.html)*

   

2. Criar uma pasta no ***C:\GitLab-Runner***

   

3. Iniciar o serviço.

   ```
   cd C:\GitLab-Runner
   .\gitlab-runner.exe install
   .\gitlab-runner.exe start
   ```

   

4. Registrar Runners.

   1. Esteja no Git, na pagina do projeto.

   2. Acesse *configurações* >> *CI/CD* >> *Executores*

      - Anote os dados da *URL* e *Token* apresentados na tela

        

5. Execute o comando

   ```
   ./gitlab-runner.exe register
   ```

   Na sequencia, preencha

   - *URL*

   - *Token*

   - *Nome da Runner*

   - *Tags que ira usar para chamar a runner*

     

6. No terminal irá aparecer a msg ´Sucesso´.

   

7. Após isso o terminal ira pedir para definir como será a forma de execução do Runner - (Docker, Shell...) 

   

8. Para conferir se esta ok, atualize a pagina de configuração do CI no Git, neste momento ira aparecer o Runner configurado.





###  Instalação MAVEN

Caso necessário para execução via terminal do projeto -  *[Instalação MAVEN](http://luizricardo.org/2014/06/instalando-configurando-e-usando-o-maven-para-gerenciar-suas-dependencias-e-seus-projetos-java/).*





###  Configuração do arquivo .gitlab-ci.yml

Para o CI conseguir executar de forma automática é necessário criar o arquivo .gitlab-ci.yml passando as execuções desejadas e as tags para a execução da runner .

Ex.:

```
stages:
  - test

test:
  stage: test
  tags:
    - shell
  script:
    - echo "Teste Automatico"
    - echo "Runner OK"
```





###  Complemento

[*Instalação GitLab-Runner](https://helpdev.com.br/2019/08/02/gitlab-como-instalar-o-gitlab-e-configurar-um-runner-para-ci-cd/)*

*[Configuração ambiente, se precisar](https://stackoverflow.com/questions/68050125/gitlab-runner-prepare-environment-failed-to-start-process-pwsh-in-windows).*





​	

