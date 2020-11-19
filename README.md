# robocopy-command

 -------------------------------------------------------------------------------
   ROBOCOPY   ::   Copie de fichiers robuste pour Windows
-------------------------------------------------------------------------------

  Début : jeudi 19 novembre 2020 19:12:32
                   Syntaxe simple :: ROBOCOPY source destination /MIR

                          source :: répertoire source (lecteur:\chemin ou
                                    \\serveur\partage\chemin).
                     destination :: rép. de destination (lecteur:\chemin ou
                                    \\serveur\partage\chemin).
                            /MIR :: met en miroir une arborescence complète.

    Pour plus d’informations sur son utilisation, exécutez ROBOCOPY /?

****  /MIR peut SUPPRIMER des fichiers en plus de les copier !
robocopy <source> <destination> [<file>[ ...]] [<options>]
https://docs.microsoft.com/fr-fr/windows-server/administration/windows-commands/robocopy









C:\Users\Stefan>ROBOCOPY /?

-------------------------------------------------------------------------------
   ROBOCOPY   ::   Copie de fichiers robuste pour Windows
-------------------------------------------------------------------------------

  Début : jeudi 19 novembre 2020 19:32:38
                         Syntaxe :: ROBOCOPY source destination [fichier
                                    [fichier]...] [options]

                          source :: répertoire source (lecteur:\chemin ou
                                    \\serveur\partage\chemin).
                     destination :: rép. de destination (lecteur:\chemin ou
                                    \\serveur\partage\chemin).
                         fichier :: fichier(s) à copier (noms/caractères
                                    génériques : valeur par défaut "*.*").

::
:: Options de copie :
::
                              /S :: copie les sous-répertoires non vides
                                    uniquement.
                              /E :: copie les sous-répertoires, y compris les
                                    vides.
                          /LEV:n :: copie uniquement les n premiers niveaux de
                                    l’arborescence source.

                              /Z :: copie les fichiers en mode de redémarrage.
                              /B :: copie les fichiers en mode de sauvegarde.
                             /ZB :: utilise le mode de redémarrage ; si
                                    l’accès est refusé, utilise le mode de
                                    sauvegarde.
                              /J :: copier à l’aide d’E/S non mises en mémoire
                                    tampon (recommandé pour les fichiers
                                    volumineux).
                         /EFSRAW :: copie tous les fichiers chiffrés en mode
                                    EFS RAW.

          /COPY:indicateurscopie :: spécifie les éléments à copier pour les
                                    fichiers (/COPY:DAT par défaut).
                       (copyflags : D=Données, A=Attributs, T=Horodatages, X=Ignorer les flux de données Alt).
                                    (S=Sécurité=ACL NTFS, O=infos prOpriétaire,
                                    U=infos d’aUdit).


                            /SEC :: copie des fichiers avec sécurité (équivaut
                                    à /COPY:DATS).
                        /COPYALL :: copie toutes les infos de fichiers
                                    (équivaut à /COPY:DATSOU).
                         /NOCOPY :: ne copie aucune info de fichier (utile
                                    avec /PURGE).
                         /SECFIX :: corrige la sécurité de tous les fichiers,
                                    même les fichiers ignorés.
                         /TIMFIX :: corrige les horodatages de tous les
                                    fichiers, même les fichiers ignorés.

                          /PURGE :: supprime les fichiers/répertoires de
                                    destination qui n’existent plus dans la
                                    source.
                            /MIR :: met en MIRoir une arborescence (équivaut
                                    à /E plus /PURGE).

                            /MOV :: déplace les fichiers (les supprime de la
                                    source après la copie).
                           /MOVE :: déplace les fichiers ET les répertoires
                                    (les supprime de la source après la copie).

                  /A+:[RASHCNET] :: ajoute les Attributs donnés aux fichiers
                                    copiés.
                  /A-:[RASHCNET] :: supprime les Attributs donnés des fichiers
                                    copiés.

                         /CREATE :: crée une arborescence et des fichiers de
                                    longueur nulle uniquement.
                            /FAT :: crée des fichiers de destination au format
                                    de nom 8.3 FAT uniquement.
                            /256 :: désactive la prise en charge des chemins
                                    d’accès très longs (> 256 caractères).

                          /MON:n :: source du moniteur ; réexécuté lorsque
                                    plus de n modifications sont observées.
                          /MOT:m :: source du moniteur ; réexécuté après m
                                    minutes en cas de modification.

                   /RH:hhmm-hhmm :: heures d’exécution : heures auxquelles de
                                    nouvelles copies peuvent être lancées.
                             /PF :: vérifie les heures d’exécution Par Fichier
                                    (et non par passage).

                          /IPG:n :: délai entre les paquets (ms) pour libérer
                                    la bande passante sur les lignes bas débit.

                /SJ :: copie les jonctions comme des jonctions plutôt que comme des cibles de jonction.
                /SL :: copie les liens symboliques comme des liens plutôt que comme des cibles de lien.

                         /MT[:n] :: Effectuer des copies multi-thread avec n threads (par défaut, 8).
                                    n doit être au moins égal à 1 et non supérieur à 128.
                                    Cette option est incompatible avec les options /IPG et /EFSRAW.
                       Redirige la sortie avec l’option /LOG pour de meilleures performances.

       /DCOPY:indicateur(s)copie :: éléments à copier pour les répertoires (valeur par défaut : /DCOPY:DA).
                       (copyflags : D=Données, A=Attributs, T=Horodatages, E=EAs, X=Ignorer les flux de données Alt).

                        /NODCOPY :: ne copie aucune info de répertoire (valeur
                                    par défaut : /DCOPY:DA).

                      /NOOFFLOAD :: copier les fichiers sans utiliser le
                                    mécanisme de déchargement de copie de
                                    Windows.

          /COMPRESS :: Demander une compression réseau pendant le transfert de fichiers, si nécessaire.

::
:: Options de sélection des fichiers :
::
                              /A :: copie uniquement les fichiers où l’attribut
                                    Archive est défini.
                              /M :: copie uniquement les fichiers où l’attribut
                                    Archive est défini et le réinitialise.
                 /IA:[RASHCNETO] :: Inclut uniquement les fichiers où l’un des
                                    Attributs donnés est défini.
                 /XA:[RASHCNETO] :: eXclut les fichiers où l’un des Attributs
                                    donnés est défini.

        /XF fichier [fichier]... :: eXclut les fichiers correspondant aux
                                    noms/chemins/caractères génériques donnés.
/XD répertoires [répertoires]... :: eXclut les répertoires correspondant
                                    à des noms/chemins donnés.

                             /XC :: eXclut les fichiers Changés.
                             /XN :: eXclut les fichiers Nouveaux.
                             /XO :: eXclut les fichiers anciens.
                             /XX :: eXclut les fichiers et répertoires
                                    supplémentaires.
                             /XL :: eXclut les fichiers et répertoires
                                    solitaires.
                             /IS :: Inclut les mêmeS fichiers.
                             /IT :: Inclut les fichiers optimisés.

                          /MAX:n :: taille de fichier maximale : exclut les
                                    fichiers de taille supérieure à n octets.
                          /MIN:n :: taille de fichier minimale : exclut les
                                    fichiers de taille inférieure à n octets.

                       /MAXAGE:n :: Antériorité maximale du fichier : exclut
                                    les fichiers plus anciens que n
                                    jours/qu’une date n.
                       /MINAGE:n :: Antériorité minimale du fichier : exclut
                                    les fichiers plus récents que n
                                    jours/qu’une date n.
                       /MAXLAD:n :: dernière date d’accès MAXimale : exclut
                                    les fichiers inutilisés depuis n.
                       /MINLAD:n :: dernière date d’accès MINimale : exclut
                                    les fichiers utilisés depuis n.
                                    (si n < 1900, alors n = n jours, sinon n =
                                    date JJMMAAA).

               /FFT :: suppose des heures de fichier FAT (granularité de 2 secondes).
               /DST :: compense les différences d’heure d’été d’une heure.

                /XJ :: exclut les liens symboliques (pour les fichiers et les répertoires) et les points de jonction.
               /XJD :: exclut les liens symboliques pour les répertoires et les points de jonction.
               /XJF : exclut les liens symboliques pour les fichiers.

                /IM :: Inclure les fichiers modifiés (heures de modification différentes).
::
:: Options de nouvelle tentative :
::
                            /R:n :: nombre de tentatives après l’échec de
                                    copies : 1 million par défaut.
                            /W:n :: délai entre les tentatives : 30 secondes
                                    par défaut.

                            /REG :: enregistre /R:n et /W:n comme paramètres
                                    par défaut dans le Registre.

               /TBD :: attend la définition de Sharenames (erreur de nouvelle tentative 67).

               /LFSM :: fonctionnement en mode espace libre faible, activation de l'interruption et de la reprise de la copie (voir Remarques).

               /LFSM:n[KMG] :: /LFSM, spécifiant la taille du plancher en n [K:kilo,M:mega,G:giga] octets.

::
:: Options d’enregistrement dans le journal :
::
                              /L :: Liste uniquement : pas de copie,
                                    d’horodatage ou de suppression de fichiers.
                              /X :: signale tous les fichiers supplémentaires
                                    et pas uniquement ceux sélectionnés.
                              /V :: produit un résultat détaillé en affichant
                                    les fichiers ignorés.
                             /TS :: inclut les horodaTageS des fichiers
                                    sources dans le résultat.
                             /FP :: inclut le chemin d’accès complet des
                                    fichiers dans le résultat.
                          /BYTES :: affiche les tailles en octets.

                             /NS :: pas de taille : n’enregistre pas les
                                    tailles de fichier.
                             /NC :: pas de classe : n’enregistre pas les
                                    classes de fichier.
                            /NFL :: pas de liste de fichiers : n’enregistre
                                    pas les noms de fichiers.
                            /NDL :: pas de liste de répertoires : n’enregistre
                                    pas les noms de répertoire.

                             /NP :: pas de compteur de progression : n’affiche
                                    pas le pourcentage copié.
                            /ETA :: affiche l’heure de fin estimée de la copie
                                    des fichiers.

                    /LOG:fichier :: copie le statut dans le fichier journal
                                    (remplace le journal existant).
                   /LOG+:fichier :: copie le statut dans le fichier journal
                                    (ajoute au journal existant).

                 /UNILOG:fichier :: copie le statut dans le fichier journal en
                                    Unicode (remplace le journal existant).
                /UNILOG+:fichier :: copie le statut dans le fichier journal en
                                    Unicode (ajoute au journal existant).

                            /TEE :: résultat dans la fenêtre de la console et
                                    dans le fichier journal.

                            /NJH :: pas d’en-tête de tâche.
                            /NJS :: pas de résumé de tâche.

                        /UNICODE :: sortie au format UNICODE.

::
:: Options de tâche :
::
                   /JOB:NomTâche :: prend les paramètres du fichier de tâche
                                    nommé.
                  /SAVE:NomTâche :: enregistre les paramètres dans le fichier
                                    nommé
                           /QUIT :: arrête après traitement de la ligne de
                                    commande (pour afficher les paramètres).
                           /NOSD :: aucun répertoire source spécifié.
                           /NODD :: aucun répertoire de destination spécifié.
                             /IF :: Inclut les fichiers suivants.

::
:: Remarques :
::
       L'utilisation de /PURGE ou de /MIR sur le répertoire racine du volume a précédemment causé
       l'application par Robocopy de l'opération demandée sur les fichiers du répertoire System
       Volume Information également. Ce n'est plus le cas. Si
       l'un ou l'autre est spécifié, Robocopy va ignorer tous les fichiers ou répertoires avec ce
       nom dans les répertoires source et de destination de niveau supérieur de la session de copie.

       La classification des fichiers modifiés ne s'applique que lorsque
       les systèmes de fichier source et de destination prennent en charge les horodatages de modification (par ex. NTFS)
       et que les fichiers source et de destination possèdent différentes heures de modification, mais sont
       autrement identiques. Ces fichiers ne sont pas copiés par défaut ; précisez /IM
       pour les inclure.

       L'indicateur /DCOPY:E demande que la copie de l'attribut étendu soit
       tentée pour les répertoires. Notez que Robocopy continue actuellement
       si les EA d'un répertoire n'ont pas pu être copiés. Cet indicateur n'est pas non plus inclus
       dans /COPYALL.

       Utilisation des demandes /LFSM Robocopy pour opérer en « mode d’espace libre faible ».
       dans ce mode, Robocopy s’interrompt chaque fois qu’une copie de fichier provoquerait l'
       espace libre du volume de destination pour aller au-dessous d’une valeur « Plancher », qui
       peut être explicitement spécifié par la forme LFSM:n[KMG] de l’indicateur.
       Si /LFSM est spécifié sans valeur de plancher explicite, le plancher est défini sur
       dix pour cent de la taille du volume de destination.
       mode espace libre faible est incompatible avec /MT, /EFSRAW, /B et /ZB.
