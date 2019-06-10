# zimbra-docs
Repositório para recursos do Zimbra Docs

A instação padrão do Zimbra Docs permite o idioma português brasileiro para edição e correção de documentos, conforme pode ser observado no /var/log/syslog:

Oct  2 14:52:03 docs loolwsd[35098]: Preloading dictionaries: Whitelisted languages: de_DE en_GB e n_US es_ES fr_FR it nl *pt_BR* pt_PT ru
 
Porém, o dicionário não vem instalado por padrão, como também pode ser observado no /var/log/syslog:

Oct  2 09:16:30 docs loolwsd[32458]: Preloading thesauri: en_US fr_FR en_GB es_ES
 
Para instalar o dicionário, deve-se efetuar o download do dicionário oficial neste repositório ou no projeto LibreOffice, no seguinte link:

https://github.com/LibreOffice/dictionaries/tree/master/pt_BR
 
O download deve ser efetuado no diretório /opt/zimbra/docs/zimbra-docs-core/share/extensions e o dicionário deve ficar no diretório dict-pt_BR. Para que o dicionário seja carregado, é necessário reiniciar o serviço:

systemctl restart zimbra-docs-server
 
O dicionário pt_BR deve aparecer como carregado no log:

Oct  2 14:52:04 docs loolwsd[35098]: Preloading thesauri: en_US fr_FR *pt_BR* en_GB es_ES
