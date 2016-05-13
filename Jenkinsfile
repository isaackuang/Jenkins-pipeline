node('node') {

    def err = null
    currentBuild.result = "SUCCESS"

    try {

      stage 'Checkout'

      stage 'Test'
        env.NODE_ENV = "test"


        sh 'echo "test environment."'
        sh 'date'

      stage 'approve'
      
          input message: 'Do you want to deploy?', ok:'Deploy', submitter: 'ops'

      stage 'Deploy'

        echo 'Deploy images.'

    }

    catch (caughtError) {

      err = caughtError
      currentBuild.result = "FAILURE"

    }

    finally {

        if (err) {

        throw err

        }
    }

}
