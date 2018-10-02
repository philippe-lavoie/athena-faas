# athena-faas
This is an [http://www.openfaas.com](OpenFaas) for [https://github.com/arachnys/athenapdf](AthenaPDF). This project is deployed inside [https://hub.docker.com/r/philippelavoie/athenapdf-faas/](docker hub). 

To use this inside OpenFaas, follow the normal flow:
- Login

  ```shell
  export GW_PASS=YourSecretPassword
  echo -n $GW_PASS | faas-cli login --username=admin --password-stdin
  ```
  
- Deploy. In this case, I'm deploying to a local kubernetes instance created with Docker.

  ```shell
  faas-cli deploy --image philippelavoie/athenapdf-faas --name athena -g http://localhost:31112
  ```

- Test. In this particular case, I'm sending the html file cliNodeTest.htl to the athena function and sending the result to result.pdf.

  ```shell
  cat cliNodeTest.html | faas-cli invoke athena > result.pdf
  ```


