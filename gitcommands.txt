git add *
git commit -m "Nome Commit"
git push origin master
 ----------------------------- Criar nova Branch
git checkout -b branch-nova
 ----------------------------- Publicar na Branch
git push origin branch-nova
 ----------------------------- Listar Branchs
git branch -a (shows both local and remote branches.)
git branch --list
git branch --show-current
 ----------------------------- Push na Branch
git push origin branch-novo
 ----------------------------- Deletar Branch Local
git branch -d localBranchName
 ----------------------------- Merge com a Master
git checkout master (Mudar para Master)
git merge branch-novo (Mostra as alterações)
git add *
git commit -m "teste branch novo"
got push origin master
------------------------------- Pull de uma branch espefica
git pull origin dev
------------------------------- Clone de uma branch espefica
git clone --single-branch --branch <branchname> <remote-repo>
git clone --single-branch --branch redesign https://git-codecommit.sa-east-1.amazonaws.com/v1/repos/empresarial-portal-atendimento-front-end-web
 ------------------------------ Help
git help
git help -a
git help <command>
 ----------------------------- Outros Comandos
git status

git remote add origin git@erickocrs/adopets-erick-test.git


git checkout --

git stash
git stash apply ?

branch errada com o git stash salva

git diff --check

git lenghts git leans pra saber quem mandou o commit

git merge ---continue ?
--------------------------------------

Para mergear sem fazer o commit (se quiser resolver algo antes)
git merge --no-ff --no-commit "branch"

---- reseta branch pela origem
git reset --hard origin/master



git remote show origin