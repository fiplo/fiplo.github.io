<!-- classes: title -->

![Redis](https://redis.com/wp-content/uploads/2021/08/redis-logo.png)

<!-- block-start: grid-->

<!-- block-start: column -->
        Pristato:

<!-- block-end -->

<!-- block-start: column -->
    Paulius Ratkevičius 
    Viktoras Dechtiar
<!-- block-end -->

<!-- block-end -->

---

<!-- contents -->

---
<!-- section-title: Kas yra Redis? -->

# <font color="#cd5d57">Redis</font>

<!-- fragments-start -->

## <font color="#cd5d57">Re</font>mote 

## <font color="#cd5d57">Di</font>ctionary 

## <font color="#cd5d57">S</font>erver
<!-- fragments-end -->

---
<!-- section-title: Kodėl Redis? -->
# Kodėl Redis?

## Žaibiškai greitas ⚡

Internetiniai servisai eksponentiškai turi didėjanti klientų kiekį, tradicinės reliacinės duomenų bazės netinkamos šiuolaikiniams projektams.

---

![Internet Usage](https://blog.cloudflare.com/content/images/2020/04/Screenshot-2020-04-20-at-18.27.41.png)


---

<!-- section-title: Ką galiu talpinti? -->
# Ką galiu talpinti?

![Data Structures](https://redis.com/wp-content/uploads/2020/06/key-value-data-stores-2-v2-920x612.png)

---

<!-- section-title: Kaip naudotis Redis? -->

# Kaip naudotis Redis?

```sh
127.0.0.1:6379> SET rakto_pavadinimas "musu talpinama reiksme"
OK
127.0.0.1:6379> get rakto_pavadinimas
"musu talpinama reiksme"
```
---
```sh
127.0.0.1:6379> KEYS *
 1) "userBuckets"
 2) "pid:977"
 3) "pid:2324"
 4) "rakto_pavadinimas"
 5) "kitas_raktas"
 6) "pid:3816"
 7) "pid:3637"
 8) "oldFrosty"
 9) "pid:1905"
10) "pid:3495"
127.0.0.1:6379> KEYS rak*
1) "rakto_pavadinimas"
```

---

```sh
127.0.0.1:6379> SET raktas_kuris_pasibaigs_uz_5_sekundziu "slapta informacija"
OK
127.0.0.1:6379> expire raktas_kuris_pasibaigs_uz_5_sekundziu 5
(integer) 1
127.0.0.1:6379> GET raktas_kuris_pasibaigs_uz_5_sekundziu
"slapta informacija"
127.0.0.1:6379> GET raktas_kuris_pasibaigs_uz_5_sekundziu
(nil)
```

---
<!-- section-title: API -->

# API


![APIs](https://your.weebsh.it/lYxUtp53.png)

---

```js
const redis = require('redis');
const client = redis.createClient({
    host: '<hostname>',
    port: <port>,
    password: '<password>'
});

client.on('error', err => {
    console.log('Error ' + err);
});
```

```js
client.set('foo', 'bar', (err, reply) => {
    if (err) throw err;
    console.log(reply);

    client.get('foo', (err, reply) => {
        if (err) throw err;
        console.log(reply);
    });
});
```

---

<!-- section-title: Fragmentacija -->

# Redis Notifications

Atskiri kanalai kuriuose klientai prenumeruoja duombazės pakitimų įvykių sąrašą.

---

<!-- section-title: Replikavimas -->

# Redis Snapshots

Kadangi visa informacija laikoma atmintyje Redis turi automatinį snapshot funkcionalumą, kuris išsaugo atmintį diske.

Ši metodika taip pat naudojama replikuoti master duombazę į giliau esančias slave duombazes.

---

<!-- section-title: Kas naudoja Redis? -->

# Redis naudotojai

<!-- block-start: grid -->

<!-- block-start: column -->
![Twitter](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogos-download.com%2Fwp-content%2Fuploads%2F2016%2F02%2FTwitter_Logo_new.png&f=1&nofb=1)
<!-- block-end -->
<!-- block-start: column -->
![Github](https://github.githubassets.com/images/modules/logos_page/GitHub-Logo.png)
<!-- block-end -->

<!-- block-start: column -->
![snapchat](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Flogos-download.com%2Fwp-content%2Fuploads%2F2016%2F07%2FSnapchat_logo.png&f=1&nofb=1)
<!-- block-end -->

<!-- block-start: column -->
![stackoverflow](https://stackoverflow.design/assets/img/logos/so/logo-stackoverflow.png)
<!-- block-end -->

<!-- block-start: column -->
![pinterest](https://external-content.duckduckgo.com/iu/?u=https%3a%2f%2fcdn.freebiesupply.com%2flogos%2flarge%2f2x%2fpinterest-1-logo-png-transparent.png&f=1&nofb=1)
<!-- block-end -->
<!-- block-start: column -->
![weibo](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogos-download.com%2Fwp-content%2Fuploads%2F2016%2F10%2FSina_Weibo_logo.png&f=1&nofb=1)
<!-- block-end -->
<!-- block-start: column -->
![craiglist](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogos-world.net%2Fwp-content%2Fuploads%2F2021%2F02%2FCraigslist-Emblem.png&f=1&nofb=1)
<!-- block-end -->
<!-- block-start: column -->
![digg](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flogonoid.com%2Fimages%2Fdigg-logo.png&f=1&nofb=1)
<!-- block-end -->
<!-- block-end -->

---
<!-- section-title: Kiek kainuoja Redis? -->

# Redis is Free!
## Tol kol turi pakankamai atminties

---

![Redislabs](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftechcrunch.com%2Fwp-content%2Fuploads%2F2019%2F02%2FRedis-labs-logo-1.png&f=1&nofb=1)
![Pricing](https://your.weebsh.it/f4jLizQJ.png)
