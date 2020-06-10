---
ms.openlocfilehash: 7723892a33bf7dd8e475b2f696db5d9ab287e182
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602992"
---

I pacchetti aggiunti ai feed di gestione pacchetti vengono denominati in un formato informatico: `{product}-{type}-{version}` .

- **prodotto**\
Tipo di prodotto .NET da installare. Le opzioni valide sono:

  - dotnet
  - aspnetcore

- **tipo**\
Sceglie l'SDK o il Runtime. Le opzioni valide sono:

  - SDK
  - runtime

- **Versione**\
Versione dell'SDK o del runtime da installare. Questo articolo fornirà sempre le istruzioni per la versione supportata più recente. Le opzioni valide sono le versioni rilasciate, ad esempio:

  - 3.1
  - 3.0
  - 2.1

  È possibile che l'SDK/Runtime che si sta provando a scaricare non sia disponibile per la distribuzione Linux. Per un elenco delle distribuzioni supportate, vedere [dipendenze e requisiti di .NET Core](../linux.md).

### <a name="examples"></a>Esempi

- Installare il runtime di ASP.NET Core 3,1:`aspnetcore-runtime-3.1`
- Installare il runtime di .NET Core 2,1:`dotnet-runtime-2.1`
- Installare .NET Core 3,1 SDK:`dotnet-sdk-3.1`

### <a name="package-missing"></a>Pacchetto mancante

Se la combinazione di versione del pacchetto non funziona, non è disponibile. Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK. Il valore non `aspnetcore-sdk-2.2` è corretto e deve essere `dotnet-sdk-2.2` . Per un elenco delle distribuzioni Linux supportate da .NET Core, vedere [dipendenze e requisiti di .NET Core](../linux.md).
