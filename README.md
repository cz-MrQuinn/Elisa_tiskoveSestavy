# Šablony pro tisk obálek – ELISA (CNS Mělník)

Tento repozitář obsahuje `.html` šablony pro tisk obálek určené pro spisovou službu **ELISA** od společnosti **CNS a.s. Mělník**. 
Cílem projektu je usnadnit a sjednotit tisk obálek v rámci elektronické spisové služby.

## 📦 Obsah

- Šablony ve formátu `.html` vhodné pro generování z ELISA
- Různé varianty rozložení pro různé typy obálek (např. C5, DL)
- Možnost úprav CSS pro vlastní branding instituce

## 🛠 Použití

1. Vyberte požadovanou šablonu (např. `obalka-c5.html`)
2. Otevřete ji v prohlížeči a/nebo v programu pro editaci .html s živým náhledem
3. Nahraďte proměnné nebo použijte v kombinaci s výstupem ze systému ELISA


## 💡 Integrace s ELISA

Šablony jsou navrženy tak, aby byly kompatibilní s exportem dat z ELISA (např. jméno adresáta, adresa, č.j., atd.). Doporučené použití:

## 📄 Licence

Tento projekt je k dispozici pod licencí **MIT** – viz [LICENSE](./LICENSE) pro více informací.

## 🤝 Přispívání

Přispěvatelé jsou vítáni! Pokud máte vlastní varianty šablon, vylepšení stylu, nebo jiné návrhy, neváhejte vytvořit **pull request** nebo otevřít **issue**.

## 🧾 O projektu

Vytvořeno jako praktický pomocník pro práci s fyzickou poštou ve veřejné správě a podpoře digitalizace procesů. Není oficiálně spojeno se společností CNS a.s. Mělník ani se systémem ELISA.

---

## 🧾 Pomocný SQL skript pro vytěžení šablon z Databáze

```sql
SELECT
  CLOKSTANICE.POPIS
 ,stav.*
 ,STISKSEST.ID_STISKSEST
 ,STISKSEST.NAZEV
 ,STISKSEST.POPIS
FROM dbo.STISKSEST
LEFT OUTER JOIN dbo.CLOKSTANICE
  ON STISKSEST.ID_CLOKSTANICE = CLOKSTANICE.ID_CLOKSTANICE
INNER JOIN dbo.RSTAVZAZNAM stav
  ON STISKSEST.ID_RSTAVZAZNAM = stav.ID_RSTAVZAZNAM
WHERE stav.ID_RSTAVZAZNAM = 10
-- AND (CLOKSTANICE.POPIS LIKE '%jandova%' OR CLOKSTANICE.POPIS IS NULL)

```

## 🧾 Seznam položek pro 

