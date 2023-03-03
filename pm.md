# PM login

## Isac Lindholm
***
### Grupparbetet

Medarbetare är Hjalmar, Axel, Lucas. Vi skulle skappa en server som du kan skappa användare till samt logga in som är säkrad. Säkerhet användes bcrypt men skappa även en session id den gör så att du kan hoppa mellan olika sidor på sidan utan att bli utloggad. inlogningen fungerar så att man letar efter användare till data bassen sen jämför lösenorden för att se om de stämmer stämmer de så loggas man in annars blir den en error och då blir du inte inloggad. viktiga saker att tänka på då man gör en server som ska inehålla användare är just säkerheten vilket vara de stora fokuset. För att göra uppgiften fick vi ett program som kör tester för att se hur sidan gör om de t.ex skrivs fel användare fel lösenord eller att ena är rätt det gör så att de är viktigt att testa ofta. Det fans 4 olika tester som testa olika saker med.


***
### Personliga svårigheter

Hade Personligen problem med att förstå session fört men senare då jag fick de förklarart för mig började jag förstå exempel på session användning:
```
    req.session.userId = username;
```

En till sak so  va lite problematisk för mig va crypteringen men samma som session fick jag det förklarat för mig så jag fick en utöckad förstålse av den
```
router.get('/crypt/:pwd', async function (req, res, next) {
    const pwd = req.params.pwd;

    await bcrypt.hash(pwd, 10, function (err, hash) {

        console.log(hash);
        //return res.json(hash);
        return res.json({ hash });
    });

});
```
***
### Personliga saker som gick bra

gick bra för mig att se mindre stavfel had lätt att förstå då jag var på plats och fick följa med och tänka med gruppen

***

### Svårigheter

problemet då vi inte använde något för att stoppa efter en res så så den fortsatte med det time out för går bara köra 1 res per route fixade genom att göra t.ex:
```
      return res.status(401).send("Access denied");
```
return gör så att den inte fortsätter köra code som är efter.

Första gången arbete med session id vilket var då svårt att förstå i början men fick mer förstålse efter tag då man bekantar sig med det.

Titta igenom en extra gång för att se till att det inte finns något fleskrivet på något som gör att code går inte att köra.
***
### Bra saker

allt gick bra de flöt på fanns mest bara lite små putsning vi gick igenom sakerna steg för steg 