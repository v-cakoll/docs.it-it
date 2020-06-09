---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602985"
---

<span data-ttu-id="0de65-101">Se viene visualizzato un messaggio di errore simile a **non è possibile individuare il pacchetto {Netcore-Package}**, eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0de65-101">If you receive an error message similar to **Unable to locate package {netcore-package}**, run the following commands.</span></span>

<span data-ttu-id="0de65-102">Nel set di comandi seguente sono presenti due segnaposto.</span><span class="sxs-lookup"><span data-stu-id="0de65-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="0de65-103">Rappresenta il pacchetto .NET Core che si sta installando, ad esempio `aspnetcore-runtime-3.1` .</span><span class="sxs-lookup"><span data-stu-id="0de65-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="0de65-104">Viene usato nel `sudo apt-get install` comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0de65-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="0de65-105">Che rappresenta la versione di Linux in cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="0de65-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="0de65-106">Viene usato nel `wget` comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0de65-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="0de65-107">Provare a pulire l'elenco dei pacchetti:</span><span class="sxs-lookup"><span data-stu-id="0de65-107">Try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

<span data-ttu-id="0de65-108">Se questa operazione non funziona, è possibile eseguire un'installazione manuale con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0de65-108">If that doesn't work, you can run a manual install with the following commands:</span></span>
