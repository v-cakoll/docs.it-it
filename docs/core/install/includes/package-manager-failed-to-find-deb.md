---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602985"
---

Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto {Netcore-Package}**, eseguire i comandi seguenti.

Nel set di comandi seguente sono presenti due segnaposto.

- `{dotnet-package}`\
Rappresenta il pacchetto .NET Core che si sta installando, ad esempio `aspnetcore-runtime-3.1` . Viene usato nel `sudo apt-get install` comando riportato di seguito.

- `{os-version}`\
Che rappresenta la versione di Linux in cui si è connessi. Viene usato nel `wget` comando riportato di seguito.

Provare a pulire l'elenco dei pacchetti:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

Se questa operazione non funziona, è possibile eseguire un'installazione manuale con i comandi seguenti:
