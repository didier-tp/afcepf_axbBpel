dans un projet de facet "Bpel"
new other.../ BPEL2 / BPEL Process File

From Template
nom de process: axb
namespace : http://bpel.dja.afcepf.fr/  (différent du namsespace des WS java)

Template Synchrone (et pas asynchrone)
...
Finish


url à ajuster dans axbArtifacts.wsdl:
   http://localhost:8282/ode/processes/axb  (ou autre)
   
======
pour générer le fichier deploy.xml spécifique à ODE 
new other ... / BPEL2 / BPEL deployement descriptor
puis choisir autre chose que none dans listes déroulantes de la partie "inbound"
puis sauvegarder.   
