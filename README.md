# example.pirati.cz

Tento web slouží jako výchozi stanice pro tvorbu dalších webu. Ať už regionálních nebo specializovaných celostátních.
Nebojte se cokoliv přiohnout, koukejte se do dalšich pirátských webů o featurach které se vám líbí a přidejte si je do svého.

Pokud byste z tohoto našeho chtěli vyjít pro tvorbu webu svého místního sdružení, změňte následující:

- v souboru `_config.yml` změňte hodnoty v horní části (title, description, url)
- v souboru `_data/links.yaml` změňte hodnoty proměnných, aby se místo pražských věcí zobrazovaly vaše místní
- přidejte tmavý obrázek `assets/img/header/background.jpg` velikost cca 1920 × 829  na něm bude bílí text z daty z links.yaml
- v adresáři `_people` odstraňte naše lidi a místo toho založte vlastní
- v adresáři `assets/img/people` dejte fotky vašich lidí. Pokud nemáte fotku, používejte `assets/img/people/ppp.jpg`
- v `_lide/index.html` můžete vybrat kreté skupiny lidí se ojeví na stránce lide
- v adresáři `_posts` odstraňte vzorový blogové příspěvek a dávejte vlastní
- v adresáři `assets/img/posts` odstraňte naše fotky pro blogové příspěvky a dávejte vlastní

Pokud chcete více přispůsobovat:
- odkazy v horním řádku mění v `_data/top-menu.yml`.
- menu pod ním je v `_includes/header`.


Jekyll se dá rozběhat nejen na Linuxu, jak se píše níže, ale docela snadno i na macOS a s trochou úsilí i na Windows 10. Návod je například v readme [Pardubického kraje](https://github.com/pirati-web/pardubicky.pirati.cz).

## Lokální spuštění

Instalace na Fedora 25: 
```
sudo dnf group install "C Development Tools and Libraries"
sudo dnf install ruby-devel
sudo dnf install rubygem-jekyll
```

Instalace Ubuntu 16.04:

```
sudo apt-get install ruby-dev gcc make libghc-zlib-dev
gem install rubygems-update
gem install jekyll bundler
bundle
```

Repozitář můžeme naklonovat do jakékoliv složky (nemusí být ve `/var/www/`).

`jekyll serve`, což stránku zkompiluje, spustí a ještě je stránka přístupná skrz localhost: `http://127.0.0.1:4000`

Popřípadě můžeme spustit jen: `jekyll build`, což do složky `_site` připraví kompletní web (ten můžeme otevřít z prohlíže pomocí klavesové zkratky `ctrl+o`).

## Struktura

Samotné stránky jsou v markdownu nebo v html (složitější struktura, např. vícesloupců apod)

Kolekce jsou markdown soubory s yaml frontend v přísliušné složce, na webu jsou použity 4:

- posts (články)
- people (lidé)
- program
- teams (týmy)

Některé údaje jsou uvedeny v složce `_data`. Jsou zde ve formátu yaml nebo json.

**CSS** je ve složce `_sass` a je automaticky kompilováno a minifikován do jednoho souboru `main.css`.

**JavaScript** je ve složce `_include/js`. Knihovny jsou linkovány skrze CDN v minifikované podobě. Další JS je v spojen do jednoho scriptu bez minifikace (zatím).

Jekyll má velmi podrobnou [dokumentaci](http://jekyllrb.com/docs/home/). A při vývoji též doporučuji [cheat sheet](http://jekyll.tips/jekyll-cheat-sheet/)
Example web which use jekyll-pirati-theme. You can modify it to your region web.

Editujte branch `gh-pages`, jejíž obsah se po commitu automaticky přegeneruje na [github.io](https://pirati-web.github.io/nazev-repozitare). Po zkontrolování, že vše funguje, udělejte pull request do branch `master`.


