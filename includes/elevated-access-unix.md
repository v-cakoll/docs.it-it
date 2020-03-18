---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "67540108"
---
### <a name="install-the-global-tool"></a>Installare lo strumento globale

Gli asset dei pacchetti devono essere installati in un percorso protetto tramite l'opzione `--tool-path`. Questa separazione consente di evitare la condivisione di un ambiente utente con restrizioni in un ambiente con privilegi elevati.

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

`/usr/local/share/dotnet-tools` verrà creato con l'autorizzazione `drwxr-xr-x`. Se la directory è già esistente, usare il comando `ls -l` per verificare se l'utente con restrizioni non dispone dell'autorizzazione per modificare la directory. In questo caso, usare il comando `sudo chmod o-w -R /usr/share/dotnet-tools` per rimuovere l'accesso.

### <a name="run-the-global-tool"></a>Eseguire lo strumento globale

**Opzione 1**: usare il percorso completo con sudo:

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

**Opzione 2**: aggiungere il collegamento al simbolo dello strumento, una volta per ogni strumento:

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

Eseguire con il comando seguente:

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Disinstallare lo strumento globale

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Se è stato creato un collegamento al simbolo, è necessario rimuovere anche questo collegamento:

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
