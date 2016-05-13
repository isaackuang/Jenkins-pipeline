node('node') {

    def err = null
    currentBuild.result = "SUCCESS"

    try {

      stage 'Checkout'

      stage 'Test'
        env.NODE_ENV = "test"


        sh 'echo "test environment."'
        sh 'echo "hello world."'

      stage 'approve'

          input message: "Is OK ?"

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
