## Git

Git je verzovací systém, bez kterého se dnes už žádný pořádný programátor neobejde. Najdete jej na adrese [git-scm.com](https://git-scm.com). Git také funguje na všech operačních systémech, na každém se ale instaluje trochu jinak. Následujte tedy návod niže podle systému na vašem počítači. **Pokud máte starší verzi gitu, než je 2.39.2, zaktualizujte Git** na nejnovější verzi. Nedávno byla v Gitu objevena bezpečnostní chyba, která je v aktuálníverzi opravena.

### Windows

Instalátor Gitu si stáhnete na stránce [git-scm.com](https://git-scm.com). Během instalace se budete muset proklikat 12 obrazovkami nastavení 🤯. Naštěstí můžete všechny nechat tak, jak jsou, až na jednu, kterou je třeba nastavit jako na obrázku.

::fig[Git PATH]{src=assets/git-path.png size=70}

### Mac OS

Na Macu by mělo stačit spustit terminál a napsat do něj příkaz `git --version`. Pokud nemáte Git již naistalovaný, tak by měl systém sám spustit průvodce instalací. Pokud nevíte co je terminál a jak do něj napsat příkaz, počkejte s instalací Gitu na následující lekci.

### Linux (Ubuntu, Debian)

Stačí do terminálu napsat `sudo apt install git`.

### Ověření instalace

Až Git nainstalujete, ověřte jeho funkčnost tak, že z příkazového řádku ([nápověda je v další lekci](https://kodim.cz/kurzy/daweb/priprava/klavesnice-terminal/terminal)) spustíte příkaz:

```bash
git --version
```

Pokud příkaz vypíše starší verzi, než je 2.39.2, Git si zaktualizujte na nejnovější verzi.

## Účet na GitHubu

GitHub je služba poskytující zdarma úložiště pro vaše projekty. Pokud chcete svůj projekt sdílet s ostatními nebo na něm pracujete ve více lidech, nemůžete jej mít uložený jen tak u sebe na počítači. Tam by k němu ostatní neměli přístup a taky byste o data mohli snadno přijít. Abyste mohli GitHub používat, je třeba si na něm založit účet.

Účet na GitHubu si vytvoříte přimo na stránce [github.com](https://github.com). Váš účet je vždy veřejný a slouží jako jakási programátorská vizitka. Můžete se díky němu se světem podělit o to, na jakých zajímavých projektech pracujete, a hezký GitHub profil může být dobrá součást vašeho životopisu. Věnujte tedy při registraci myšlenku volbě uživatelského jména. Pomocí GitHub účtu se také budete přihlašovat na tyto stránky a získáte přístup k neveřejným materiálům v této akademii.
