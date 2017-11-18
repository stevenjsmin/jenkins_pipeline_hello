node {
   stage 'Stage 1'
   		echo 'Hello World 1'
   stage 'Stage 2'
   		echo 'Hello World 2'
   stage 'Stage 3'
   		echo 'Hello World 3'

    sh 'git name-rev --name-only HEAD > GIT_BRANCH'
    sh 'cat GIT_BRANCH'
    git_branch = readFile('GIT_BRANCH').trim()
    env.GIT_BRANCH = git_branch
   currentBuild.description = "#${BUILD_NUMBER}-${env.GIT_BRANCH}"

}