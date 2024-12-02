# Front

### Ligne de requête
Chaque requête HTTP commence par la ligne de requête.

Celle-ci se compose de la méthode HTTP, de la ressource demandée et de la version du protocole HTTP.

```GET /home.html HTTP/1.1````

Dans cet exemple,GET est la méthode HTTP,```/home.html``` est la ressource demandée et HTTP 1.1 est le protocole utilisé.

### Méthodes HTTP
Les méthodes HTTP indiquent l'action que le client souhaite effectuer sur la ressource du serveur web.

Les méthodes HTTP les plus courantes sont les suivantes :

| Méthode HTTP |  Description de la méthode  | 
|:-----|:--------:|
| GET   | Le client demande une ressource sur le serveur web. |
| POST   | Le client soumet des données à une ressource sur le serveur web. | 
| PUT   |Le client remplace une ressource sur le serveur web. |
| DELETE   |Le client supprime une ressource sur le serveur web. |
| PATCH   | Le client met partiellement à jour une ressource sur le serveur web. |

### En-têtes de requête HTTP
Après la ligne de requête, les en-têtes HTTP sont suivis d'un saut de ligne.

Il existe plusieurs possibilités d'inclure un en-tête HTTP dans la requête HTTP. Un en-tête est un nom insensible à la casse, suivi d'une adresse: et d'une valeur.

Les en-têtes les plus courants sont les suivants :

```
Host: example.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: */*
Accept-Language: en
Content-type: text/json

```

| en-tête |  Description   | 
|:-----|:--------:|
| Host   | spécifie l'hôte du serveur et indique où la ressource est demandée.|
| User-Agent   | informe le serveur web de l'application à l'origine de la requête. Il inclut souvent le système d'exploitation (Windows, Mac, Linux), la version et le fournisseur de l'application.| 
|Accept   |indique au serveur web le type de contenu que le client acceptera en réponse. |
| Accept-Language   |indique la langue et éventuellement la locale que le client préfère. |
| Content-type    | indique le type de contenu transmis dans le corps de la requête. |

Corps de la requête HTTP
Les requêtes HTTP peuvent éventuellement inclure un corps de requête. Un corps de requête est souvent inclus lors de l'utilisation des méthodes HTTP POST et PUT pour transmettre des données.

```
POST /users HTTP/1.1
Host: example.com

{
 "key1":"value1",
 "key2":"value2",
 "array1":["value3","value4"]
}
```
```
PUT /users/1 HTTP/1.1
Host: example.com
Content-type: text/json

{"key1":"value1"}
```
Réponses HTTP
Lorsque le serveur web a fini de traiter la requête HTTP, il renvoie une réponse HTTP.

La première ligne de la réponse est la ligne d'état. Cette ligne indique au client si la demande a abouti ou si une erreur s'est produite.

HTTP/1.1 200 OK 

La ligne commence par la version du protocole HTTP, suivie du code d'état et d'une phrase de raison. La phrase d'explication est une représentation textuelle du code d'état.

Codes d'état HTTP
Le premier chiffre d'un code d'état HTTP indique la catégorie de la réponse : Information, Succès, Redirection, Erreur du client ou Erreur du serveur.

Les codes d'état courants que vous rencontrerez pour chaque catégorie sont les suivants :

1XX Information

| Code d'état |  Phrase de raison  | Description de l'état |
|:-----|:--------:|------:|
| 100   | Continuer | Le serveur a reçu les en-têtes de la demande et doit continuer à envoyer le corps de la demande.|
| 101   |  Changement de protocole  |   Le client a demandé au serveur de changer de protocole et le serveur a accepté de le faire.|



2XX Succès

| Code d'état |  Phrase de raison  | Description de l'état |
|:-----|:--------:|------:|
| 200   | OK | Réponse standard renvoyée par le serveur pour indiquer qu'il a traité la demande avec succès.|
| 201   | Créé |   Le serveur a traité la demande avec succès et une ressource a été créée.|
| 202   | Accepté |   Le serveur a accepté de traiter la demande, mais le traitement n'est pas encore terminé.|
| 204   | Pas de contenu |   Le serveur a traité la demande avec succès mais ne renvoie aucun contenu.|


3XX Redirection

| Code d'état |  Phrase de raison  | Description de l'état |
|:-----|:--------:|------:|
| 301   | Déplacé de façon permanente | Cette demande et toutes les demandes futures doivent être envoyées à l'emplacement renvoyé.|
| 302   | Trouvé |   Cette demande doit être envoyée à l'emplacement retourné.|

4XX Erreur du client


| Code d'état |  Phrase de raison  | Description de l'état |
|:-----|:--------:|------:|
| 400   | Mauvaise demande | Le serveur ne peut pas traiter la demande en raison d'une erreur du client, par exemple une demande non valide ou des données transmises trop volumineuses.|
| 401   | Non autorisé |   Le client qui fait la demande n'est pas autorisé et doit s'authentifier.|
| 403   | Interdit |  La demande était valide mais le serveur refuse de la traiter. Ce refus est généralement dû au fait que le client ne dispose pas d'autorisations suffisantes pour le site web, par exemple s'il demande une action d'administrateur alors que l'utilisateur n'est pas administrateur.|
| 404   | Non trouvé |   Le serveur n'a pas trouvé la ressource demandée.|
| 405   | Méthode non autorisée |   Le serveur web ne prend pas en charge la méthode HTTP utilisée.|

5XX Erreur du serveur

| Code d'état |  Phrase de raison  | Description de l'état |
|:-----|:--------:|------:|
| 500   | Erreur interne du serveur | Code d'état d'erreur générique donné lorsqu'une erreur ou une condition inattendue s'est produite lors du traitement de la demande.|
| 502   | Mauvaise passerelle |   Le serveur web a reçu une réponse non valide du serveur d'application.|
| 503   | Service indisponible |   Le serveur web ne peut pas traiter la demande.|


### En-têtes de réponse HTTP
Après la ligne d'état, il y a des en-têtes de réponse HTTP optionnels suivis d'un saut de ligne.

Comme pour les en-têtes de requête, de nombreux en-têtes HTTP peuvent être inclus dans la réponse HTTP.

Les en-têtes de réponse les plus courants sont les suivants :

```
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html
```
| en-tête |  Description   | 
|:-----|:--------:|
|  Date   | indique la date et l'heure auxquelles la réponse HTTP a été générée.|
| Server   | décrit le logiciel du serveur web utilisé pour générer la réponse.| 
|Content-Length  |décrit la longueur de la réponse. |
| Content-Type   | décrit le type de média de la ressource renvoyée (par exemple, document HTML, image, vidéo). |
| Content-type    | indique le type de contenu transmis dans le corps de la requête. |


Corps de la réponse HTTP
Le corps de la réponse HTTP suit les en-têtes de la réponse HTTP. Il s'agit du contenu principal de la réponse HTTP.

Il peut contenir des images, des vidéos, des documents HTML et d'autres types de médias.

```
HTTP/1.1 200 OK
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html

<html>
  <head><title>Test</title></head>
  <body>Test HTML page.</body>
</html>
```
