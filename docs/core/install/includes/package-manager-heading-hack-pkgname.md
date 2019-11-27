---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450884"
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

  - 3.0
  - 2.2
  - 2.1

### <a name="examples"></a>Esempi

- Installare .NET Core 2,2 SDK: `dotnet-sdk-2.2`
- Installare il runtime di ASP.NET Core 3,0: `aspnetcore-runtime-3.0`
- Installare il runtime di .NET Core 2,1: `dotnet-runtime-2.1`

### <a name="troubleshoot"></a>Risoluzione dei problemi

Se la combinazione di pacchetti non funziona, non è disponibile. Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK. Il valore `aspnetcore-sdk-2.2` non è corretto e deve essere `dotnet-sdk-2.2`
