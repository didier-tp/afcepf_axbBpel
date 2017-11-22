Mode opératoire global (l'ordre est important) :
================================================
1) préparer tous les fichiers WSDL (avec parties plnk:partnerLinkType et xmlns:plnk )
    - effectuer une copie locale calcul.wsdl du WSDL du service java à appeler (...?wsdl)
      (code source page et copier/coller)
    - ajouter xmlns:plnk et plnk:partnerLinkType via un copier/coller adapté de axbArtifacts.wsdl
2) ajouter les <bpel:import …. "….wsdl" /> dans le haut du fichier bpel
   - ajuster le namespace
   - ajouter xmlns:nsc="http://ws.dja.afcepf.fr/" ou equivalent
     sur la balise principale <process > du fichier .bpel
3) ajouter/paramétrer les "partnerLink" (avec myRole="roleBpel" ou
partnerRole="RoleExterne" )
4) ajouter les variables "bpel" basées sur des types de messages WSDL (variables xxxInput
et xxxOutput pour chaque opération à invoquer)
5) ajouter et paramétrer tous les "invoke …" dans une séquence du BPEL
   (penser à decocher "use WSDL ..." pour choisir variables ...input et ...ouput
6) ajouter et paramétrer tous les "assign / copy/from" selon l'algorithme du processus.
(Bien penser à initialiser la variable "output" du reply du processus bpel et les
variables"xxxInput" de chaque opération invoquée : To = variable/payload ,
From=fixed_value).
7) peaufiner le fichier deploy.xml (en sélectionnant à la place de none) 