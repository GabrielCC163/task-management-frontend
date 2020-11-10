# Configuração de Deploy no AWS S3

1. Crie um Bucket no serviço S3, com um nome único (ex: nestjs-task-management-frontend-grodrigues) desabilitando a opção **Bloquear todo o acesso público**.

2. Clique sobre o bucket recém criado e em Propriedades > Hospedagem de site estático > Editar > Ativar.

3. Digite index.html no campo Documento de índice e clique em Salvar alterações.

4. Clique em Permissões e no campo Política do bucket digite:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::example.com/*"
            ]
        }
    ]
}
```

Subtitua example.com pelo nome do bucket.
