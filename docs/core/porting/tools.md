---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 64bad7600d8e17ada83d4bd8bc56762fd1789f43
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989129"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Strumenti di supporto per la portabilità in .NET Core

Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:

- [.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) una catena di strumenti che può generare un report sulla portabilità del codice tra .NET Framework e .NET Core:
  - Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)
  - Come [estensione](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) di Visual Studio
- [Analizzatore di API .NET:](../../standard/analyzers/api-analyzer.md) analizzatore Roslyn che individua i potenziali rischi di compatibilità per le API di C' su piattaforme diverse e rileva le chiamate alle API deprecate.

È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING]
> CsprojToVs2017 è uno strumento di terze parti. Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende. CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati. Non è una soluzione garantita per la migrazione dei formati di file di progetto.
