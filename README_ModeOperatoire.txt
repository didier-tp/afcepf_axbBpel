Mode op�ratoire global (l'ordre est important) :
================================================
1) pr�parer tous les fichiers WSDL (avec parties plnk:partnerLinkType et xmlns:plnk )
    - effectuer une copie locale calcul.wsdl du WSDL du service java � appeler (...?wsdl)
      (code source page et copier/coller)
    - ajouter xmlns:plnk et plnk:partnerLinkType via un copier/coller adapt� de axbArtifacts.wsdl
2) ajouter les <bpel:import �. "�.wsdl" /> dans le haut du fichier bpel
   - ajuster le namespace
   - ajouter xmlns:nsc="http://ws.dja.afcepf.fr/" ou equivalent
     sur la balise principale <process > du fichier .bpel
3) ajouter/param�trer les "partnerLink" (avec myRole="roleBpel" ou
partnerRole="RoleExterne" )
4) ajouter les variables "bpel" bas�es sur des types de messages WSDL (variables xxxInput
et xxxOutput pour chaque op�ration � invoquer)
5) ajouter et param�trer tous les "invoke �" dans une s�quence du BPEL
   (penser � decocher "use WSDL ..." pour choisir variables ...input et ...ouput
6) ajouter et param�trer tous les "assign / copy/from" selon l'algorithme du processus.
(Bien penser � initialiser la variable "output" du reply du processus bpel et les
variables"xxxInput" de chaque op�ration invoqu�e : To = variable/payload ,
From=fixed_value).
7) peaufiner le fichier deploy.xml (en s�lectionnant � la place de none) 