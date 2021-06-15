# Dojo Git

## Introdução:

1. O que é git?

2. O que é github?

3. O que é repositório remoto vs repsitório local?

4. O que é branch?

5. O que é commit?

6. O que é merge?

7. O que é pull request?

## Instalação

### Windows:
- Instale o bash do git no windows por esse link: https://gitforwindows.org/

### Linux:
- O git vem instalado por default no linux, mas para instalar basta:

    ```$ sudo apt update ```

    ```$ sudo apt install git ```

### MacOS:

- Instale o gerenciador de pacotes do mac **homebrew**:

   ```$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" ```

- Instale o git pelo homebrew:

    ```$  brew install git```


## Comando


1. Clonar o repositório para o ambiente local:

   ``` $ git clone https://github.com/lucianaribeiro/git-dojo.git ```

2. Entre no seu repositório local:

    ```$ cd git-dojo```

3. Configure seu nome e email do git:

    ```git config --global user.name "Seu Nome"```

    ```git config --global user.email "seuemaildogit@email.com"```

4. Veja o status da sua branch:

   ```$ git status ```

5. Crie a sua própria *branch* localmente:

    ```$ git checkout -b seunome ```

6. Veja o status da sua nova branch:

   ```$ git status ```

7. Crie um arquivo .txt com seu nome

8. Adicione o seu arquivo para que o git possa encontrá-lo:

    ```$ git add nomedoarquivo.txt ```

9. Hora de commitar o arquivo modificado para a sua branch local:

    ```$ git commit ```

    a. Adicione uma mensagem significativa no commit:

    ```feat(NomeDoArquivo): O que foi feito no arquivo```

10. O seu commit foi feito localmente, para visualizá-lo:

   ```$ git log```

11. Atualize sua branch com a branch main:

    ```$ git checkout main```

    ```$ git pull origin main```

12. Volte pra a sua brach

    ```$ git checkout seunome```

13. Dê um merge da sua branch com a main 

    ```$ git merge main```

14. Envie o seu commit para o repositório remoto:

    ```$ git push origin seunome```

15. Abra um pull request para a branch main



## Avançado

Trabalhando com *rebase*:

1. Modifique o arquivo novamente e siga os passos 6 e 7 novamente.

2. Para atulaizar a sua branch com a main, mude para a branch main:

   ```$ git checkout main```

3. Atualize a branch main local com a branch main remota:

    ```$ git pull```

4. Volte para a sua branch:
   
   ```$ git checkout seunome```

5. Atualize sua branch local com a main usando rebase:

    ```$ git rebase main```

    a. Caso dê conflito, resolva os conflitos e:
        
    ```$ git add arquivosmodificados```
    
    ```$ git rebase --continue```

    b. Caso deseje abortar o rebase:
     
    ```$ git rebase --abort```

6. Envie o seu commit para o repositório remoto:

    ```$ git push -f origin seunome```

7. Rebase interativo:

    ```$ git rebase -i main```

    O rebase interativo permite que os commits em staging (que não estão na main) sejam modificados de diversas formas:

    - Edição da mensagem do commit, edição do commit em si, deleção do commit, squash de commit e etc. 

    Outras formas de fazer um rebase interativo:

    ```$ git rebase -i #hashDeUmCommit```

    ```$ git rebase -i outraBranch```

8. Reset de um commit:
    
    Para resetar um commit, a forma mais segura é utilizando o rebase interativo:

    ```$ git rebase -i main```

    - Troque `pick` por `edit` no commit desejado.

    ```$ git reset --hard origin/nomdeDaBranch```

    O commit foi resetado, mas os arquivos modificados continuam em staging, então é possível editar os arquivos e refazer o commit.

    Após finalizar as modificações, adicione e faça o commit, então:

    ```$ git rebase --continue```

9. Stash de uma modificação

    Para manter uma modificação em stash, basta:

    ```$ git stash```

    Para visulizar a lista de stashes:

    ```$ git stash list```

    Para recuperar as modifações, basta:

    ```$ git stash pop```


10. Adicionando ou modificando o ultimo commit:

    Faça a modificação necessária e:

    ```$ git commit --amend```

11. Cherry pick:

    Para inserir um commit específico de uma branch em outra branch utilize o cherry pick:

    ```$ git cherry-pick #hashdocommit```