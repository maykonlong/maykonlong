image: atlassian/default-image:3

pipelines:
  default:
    - step:
        name: Run automated API tests using Postman CLI
        script:
          # Install Postman CLI
          - curl -o- "https://dl-cli.pstmn.io/install/linux64.sh" | sh
          # Login using your API Key
          - postman login --with-api-key $POSTMAN_API_KEY
          # Run your collection using Postman CLI
          - postman collection run "21490659-fb50986d-48e1-4e0c-b354-147f3e163379" -e "21490659-1c23e5d4-42c4-4cad-b43f-96dcf1920797"
