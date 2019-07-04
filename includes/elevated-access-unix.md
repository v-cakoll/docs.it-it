---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424701"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="993ba-101">Installare lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="993ba-101">Install the global tool</span></span>

<span data-ttu-id="993ba-102">Gli asset dei pacchetti devono essere installati in un percorso protetto tramite l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="993ba-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="993ba-103">Questa separazione consente di evitare la condivisione di un ambiente utente con restrizioni in un ambiente con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="993ba-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="993ba-104">`/usr/local/share/dotnet-tools` verrà creato con l'autorizzazione `drwxr-xr-x`.</span><span class="sxs-lookup"><span data-stu-id="993ba-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="993ba-105">Se la directory è già esistente, usare il comando `ls -l` per verificare se l'utente con restrizioni non dispone dell'autorizzazione per modificare la directory.</span><span class="sxs-lookup"><span data-stu-id="993ba-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="993ba-106">In questo caso, usare il comando `sudo chmod o-w -R /usr/share/dotnet-tools` per rimuovere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="993ba-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="993ba-107">Eseguire lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="993ba-107">Run the global tool</span></span>

<span data-ttu-id="993ba-108">**Opzione 1**: usare il percorso completo con sudo:</span><span class="sxs-lookup"><span data-stu-id="993ba-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="993ba-109">**Opzione 2**: aggiungere il collegamento al simbolo dello strumento, una volta per ogni strumento:</span><span class="sxs-lookup"><span data-stu-id="993ba-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="993ba-110">Eseguire con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="993ba-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="993ba-111">Disinstallare lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="993ba-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="993ba-112">Se è stato creato un collegamento al simbolo, è necessario rimuovere anche questo collegamento:</span><span class="sxs-lookup"><span data-stu-id="993ba-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```