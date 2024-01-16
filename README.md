# Optimisation des coûts d'AWS - Identification des ressources non utilisées

## Identification des Snapchots EBS non utilisées

Dans cet exemple, nous allons créer une fonction Lambda qui identifie les Snapchots EBS qui ne sont plus associés à une instance EC2 active et les supprime pour économiser sur les coûts de stockage.

### Description:

La fonction Lambda récupère tous les Snapchots EBS appartenant au même compte ("self") et récupère également une liste d'instances EC2 actives (en cours d'exécution et arrêtées). Pour chaque instantané, elle vérifie si le volume associé (s'il existe) n'est pas associé à une instance active. S'il trouve un instantané périmé, il le supprime, ce qui permet d'optimiser les coûts de stockage.



