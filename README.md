# Alumil Solar — Εργαλεία Μηχανικού (Hub)

Μία στατική σελίδα (`index.html`) που δείχνει κάρτες για κάθε εργαλείο και ανοίγει το καθένα σε νέο tab. Δεν έχει backend, δεν χρειάζεται build — απλά αρχεία.

## Δομή φακέλων

```
alumil-solar-hub/
├── index.html              ← το hub, μην το αλλάξεις δομικά
├── tools/                   ← εδώ μπαίνουν τα html αρχεία των εργαλείων
│   ├── project-reference-list.html
│   ├── fast-table-designer.html
│   └── ss199-bom-calculator.html
└── README.md
```

**Βάλε εσύ τα τελευταία html αρχεία μέσα στο `tools/`** με ακριβώς αυτά τα ονόματα (ή άλλα, αρκεί να ταιριάζουν με το `file:` στο index.html — βλ. παρακάτω).

## Πώς προσθέτεις ένα νέο εργαλείο στο μέλλον

1. Βάλε το html αρχείο μέσα στο `tools/`.
2. Άνοιξε το `index.html`, βρες το array `TOOLS` μέσα στο `<script>`.
3. Αντίγραψε ένα block, γέμισε τα πεδία `title`, `tag` (`proj` / `draw` / `calc`), `tagLabel`, `description`, `file`, `updated`.
4. Κάνε commit & push. Τέλος — δεν αγγίζεις τίποτα άλλο στη σελίδα.

Δεν χρειάζεται server, δεν χρειάζεται JSON αρχείο ξεχωριστά· όλα ζουν μέσα στο ίδιο `index.html`, στο πρότυπο των υπόλοιπων εργαλείων σου.

## Deploy σε GitHub Pages (public repo)

1. Δημιούργησε νέο repo στο GitHub (π.χ. `alumil-solar-tools`), **public**.
2. Ανέβασε όλο τον φάκελο (`index.html`, `tools/`, `README.md`) στο branch `main`.
3. Repo → **Settings** → **Pages**.
4. Στο **Source** επίλεξε `Deploy from a branch` → branch `main`, folder `/ (root)` → **Save**.
5. Μετά από 1-2 λεπτά η σελίδα θα είναι ζωντανή στο:
   `https://<username-ή-org>.github.io/alumil-solar-tools/`
6. Αυτό το link το μοιράζεσαι με τους συναδέλφους — δεν χρειάζεται login, απλά το ανοίγουν.

### Αν το repo είναι μέσα σε GitHub Organization
Ίδια διαδικασία, απλά ίσως χρειαστεί να ενεργοποιήσεις Pages σε επίπεδο organization settings αν δεν το βλέπεις άμεσα στο repo.

## Σημείωση για public repo

Public σημαίνει ότι ο κώδικας (και τα εργαλεία μέσα στο `tools/`) είναι ορατά σε όποιον έχει το link ή βρει το repo — GitHub Pages public repos δεν έχουν password. Αν κάποιο εργαλείο έχει ευαίσθητα δεδομένα κόστους/τιμολόγησης embedded μέσα στο html (π.χ. το SS199 BoM Calculator έχει markup/τιμές), σκέψου το δύο φορές πριν το ανεβάσεις έτσι δημόσια — ή βγάλε τα ευαίσθητα νούμερα σε ξεχωριστό αρχείο πριν το push, ή κάνε το repo private αν αλλάξεις γνώμη.
