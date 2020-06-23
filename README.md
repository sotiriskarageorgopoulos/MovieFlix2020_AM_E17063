# MovieFlix
Το Movieflix είναι ένα Πληροφοριακό Σύστημα, το οποίο υλοποίησα στα πλαίσια της απαλλακτικής εργασίας του μαθήματος
Πληροφοριακά Συστήματα. 
## Λειτουργίες MovieFlix
Οι λειτουργίες που υποστηρίζει το σύστημα έιναι οι παρακάτω:
Για χρήστες και διαχειριστές:
* Εισοδος στο Σύστημα
* Εγγραφή στο Σύστημα
* Αναζήτηση Ταινίας
* Εμφάνιση Πληροφοριών Ταινίας
* Εμφάνιση Σχολίων κάθε ταινίας 
* Βαθμολόγηση κάθε ταινίας
* Αφαίρεση Βαθμολογίας
* Εισαγωγή σχολίου
* Εμφάνιση όλων των σχολίων του
* Εμφάνιση όλων των βαθμολογιών του
* Διαγραφή σχολίου του
* Διαγραφή λογαριασμού του
Για διαχειριστές:
* Εισαγωγή νέας ταινίας
* Διαγραφή ταινίας
* Ενημέρωση υπάρχουσας ταινίας
* Διαγραφή σχολίων άλλων χρηστών από μία ταινία
* Αλλαγή κατηγορίας χρήστη από απλό σε διαχειριστή
* Διαγραφή οποιουδήποτε απλού χρήστη
## Οδηγίες εγκατάστασης Movieflix
Οι οδηγίες αφορούν υπολογιστές με λειτουργικό σύστημα Ubuntu.
* Εγκατάσταση Docker στον υπολογιστή σας,με τη χρήση των παρακάτω εντολών.
  Άν είναι ήδη εγακατεστημένο μπορείται να παραλείψετε αυτό το βήμα
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
```
* Στον φάκελο app θα εκτελέστε την παρακάτω εντολή,
προκειμένου να δημιουργηθεί η εικόνα docker της εφαρμογής.
```
sudo docker build . -t movieflix
```
* Εκτέλεση ταυτόχρονα των docker containers, με χρήση της παρακάτω εντολής
```
sudo docker-compose up
```
* Στον φάκελο resources θα εκτελέσετε τις παρακάτω εντολές 
για να αντιγράψετε τα json αρχεία στην εικόνα mongo που βρίσκεται 
στο container mongodb.
```
sudo docker cp movies.json mongodb:/movies.json
sudo docker cp users.json mongodb:/users.json
```
* Δημιουργία Βάσης Δεδομένων Movieflix και των συλλογών Movies και Users, 
με τη χρήση των παρακάτω εντολών.
```
sudo docker exec -it mongodb mongoimport --db=Movieflix --collection=Users --file=users.json
sudo docker exec -it mongodb mongoimport --db=Movieflix --collection=Movies --file=movies.json
```
## Παραδείγματα εκτέλεσης του συστήματος
* Είσοδος στο σύστημα ως Απλός χρήστης:
* Αναζήτηση Ταινίας με βάση τον τίτλο:
* Αναζήτηση Ταινίας με βάση το έτος κυκλοφορίας:
* Αναζήτηση Ταινίας με βάση ηθοποιό:
* Πληροφορίες Ταινίας:
* Εισαγωγή σχολίου για μία ταινία:
* Εισαγωγή βαθμολογίας ταινίας:
* Αφαίρεση βαθμολογίας ταινίας:
* Εμφάνιση όλων των σχολίων του χρήστη:
* Εγγραφή στο Σύστημα ως απλός χρήστης:
* Εμφάνιση των σχολίων άλλων χρηστών για τη ταινία:
* Διαγραφή σχολίου:
* Διαγραφή λογαριασμού:
* Είσοδος στο σύστημα ως Διαχειριστής:
* Εισαγωγή νέας ταινίας:
* Ενημέρωση τίτλου υπάρχουσας ταινίας:
* Ενημέρωση έτους υπάρχουσας ταινίας:
* Ενημέρωση πλοκής υπάρχουσας ταινίας:
* Ενημέρωση ηθοποιών υπάρχουσας ταινίας:
* Διαγραφή ταινίας:
* Διαγραφή σχολίου άλλου χρήστη:
* Αλλαγή κατηγορίας χρήστη σε απλό διαχειριστή και διαγραφή ενός απλού χρήστη:

## Υλοποιήθηκε με:

* [Flask](https://flask.palletsprojects.com/en/1.1.x/)
* [Flask-PyMongo](https://flask-pymongo.readthedocs.io/en/latest/) 



