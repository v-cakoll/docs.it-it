---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116169"
---

I pacchetti aggiunti ai feed di gestione pacchetti vengono denominati in un formato informatico: `{product}-{type}-{version}`.

- \ **prodotto**
Tipo di prodotto .NET da installare. Le opzioni valide sono:

  - dotnet
  - aspnetcore

- **type**\
Sceglie l'SDK o il Runtime. Le opzioni valide sono:

  - SDK
  - runtime di

- \ **versione**
Versione dell'SDK o del runtime da installare. Questo articolo fornirà sempre le istruzioni per la versione supportata più recente. Le opzioni valide sono le versioni rilasciate, ad esempio:

  - 3.0
  - 2.2
  - 2.1

### <a name="examples"></a>Esempi

- Installare .NET Core 2,2 SDK: `dotnet-sdk-2.2`
- Installare il runtime di ASP.NET Core 3,1: `aspnetcore-runtime-3.1`
- Installare il runtime di .NET Core 2,1: `dotnet-runtime-2.1`

### <a name="troubleshoot"></a>Risolvere i problemi

Se la combinazione di pacchetti non funziona, non è disponibile. Ad esempio, non è disponibile un SDK ASP.NET Core, i componenti SDK sono inclusi nel .NET Core SDK. Il valore `aspnetcore-sdk-2.2` non è corretto e deve essere `dotnet-sdk-2.2`
