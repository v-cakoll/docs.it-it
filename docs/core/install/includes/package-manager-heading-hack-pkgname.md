---
ms.openlocfilehash: 4340ed7444681b4601dea50c93926b0ee0c07eec
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134128"
---

I pacchetti aggiunti ai feed del gestore di `{product}-{type}-{version}`pacchetti sono denominati in un formato comcatenabile: .

- **Prodotto**\
Tipo di prodotto .NET da installare. Le opzioni valide sono:

  - dotnet
  - aspnetcore (aspnetcore)

- **digitare**\
Sceglie l'SDK o il runtime. Le opzioni valide sono:

  - SDK
  - runtime

- **Versione**\
Versione dell'SDK o del runtime da installare. Questo articolo fornirà sempre le istruzioni per l'ultima versione supportata. Le opzioni valide sono qualsiasi versione rilasciata, ad esempio:

  - 3.1
  - 3.0
  - 2.1

  È possibile che l'SDK/runtime che si sta tentando di scaricare non sia disponibile per la distribuzione Linux. Per un elenco delle distribuzioni supportate, vedere [Dipendenze e requisiti](../dependencies.md?pivots=os-linux)di .NET Core .

### <a name="examples"></a>Esempi

- Installare il runtime di ASP.NET Core 3.1:Install the ASP.NET Core 3.1 runtime:`aspnetcore-runtime-3.1`
- Installare il runtime di .NET Core 2.1:`dotnet-runtime-2.1`
- Installare .NET Core 3.1 SDK:`dotnet-sdk-3.1`

### <a name="package-missing"></a>Pacchetto mancante

Se la combinazione pacchetto-versione non funziona, non è disponibile. Ad esempio, non esiste un ASP.NET Core SDK, i componenti SDK sono inclusi in .NET Core SDK. Il `aspnetcore-sdk-2.2` valore non è `dotnet-sdk-2.2`corretto e deve essere . Per un elenco delle distribuzioni Linux supportate da .NET Core, vedere Dipendenze e requisiti di [.NET Core.](../dependencies.md?pivots=os-linux)
