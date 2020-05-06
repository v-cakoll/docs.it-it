---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795586"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Strumenti di supporto per la portabilità in .NET Core

Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:

- [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) : una procedura di base che consente di generare un report sulla portabilità del codice tra .NET Framework e .NET Core:
  - Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)
  - Come [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) : un analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# su piattaforme diverse e rileva le chiamate alle API deprecate.
- [try-Convert](https://www.nuget.org/packages/try-convert/) : strumento globale .NET Core in grado di convertire un progetto o un'intera soluzione in .NET SDK, incluso lo strumento per lo trasferimento di app desktop a .NET Core. Non è consigliabile se è stata stabilita una compilazione più complessa (ad esempio, le attività, le destinazioni o le importazioni personalizzate) e vengono rifiutati molti tipi di progetto non compatibili con .NET Core.
