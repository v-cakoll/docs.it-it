---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77465956"
---

I pacchetti aggiunti ai feed di gestione pacchetti vengono denominati in un formato informatico: `{product}-{type}-{version}`.

- \ **prodotto**
Tipo di prodotto .NET da installare. Le opzioni valide sono:

  - dotnet
  - aspnetcore

- **digitare**\
Sceglie l'SDK o il Runtime. Le opzioni valide sono:

  - SDK
  - runtime

- \ **versione**
Versione dell'SDK o del runtime da installare. Questo articolo fornirà sempre le istruzioni per la versione supportata più recente. Le opzioni valide sono le versioni rilasciate, ad esempio:

  - 3.1
  - 3.0
  - 2.1

  È possibile che l'SDK/Runtime che si sta provando a scaricare non sia disponibile per la distribuzione Linux. Per un elenco delle distribuzioni supportate, vedere [dipendenze e requisiti di .NET Core](../dependencies.md?pivots=os-linux).

### <a name="examples"></a>Esempi

- Installare il runtime di ASP.NET Core 3,1: `aspnetcore-runtime-3.1`
- Installare il runtime di .NET Core 2,1: `dotnet-runtime-2.1`
- Installare .NET Core 3,0 SDK: `dotnet-sdk-3.0`

### <a name="package-missing"></a>Pacchetto mancante

Se la combinazione di versione del pacchetto non funziona, non è disponibile. Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK. Il valore `aspnetcore-sdk-2.2` non è corretto e deve essere `dotnet-sdk-2.2`. Per un elenco delle distribuzioni Linux supportate da .NET Core, vedere [dipendenze e requisiti di .NET Core](../dependencies.md?pivots=os-linux).
