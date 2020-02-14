---
title: Strumenti per la portabilità in .NET Core
description: Informazioni su alcuni degli strumenti che è possibile usare per la portabilità in .NET Core
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 3b71c31b4f26b278b2bd1088adc8e9f64d28ab7b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215188"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Strumenti di supporto per la portabilità in .NET Core

Gli strumenti descritti in questo articolo possono risultare utili per la portabilità di:

- [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) : una procedura di base che consente di generare un report sulla portabilità del codice tra .NET Framework e .NET Core:
  - Come [strumento da riga di comando](https://github.com/Microsoft/dotnet-apiport/releases)
  - Come [estensione di Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)
- [Analizzatore di API .NET](../../standard/analyzers/api-analyzer.md) - Analizzatore Roslyn che individua potenziali rischi di compatibilità per le API C# in piattaforme diverse e rileva le chiamate alle API deprecate.

È anche possibile provare a convertire soluzioni più piccole o singoli progetti al formato di file di progetto .NET Core con lo strumento [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).

> [!WARNING] 
> CsprojToVs2017 è uno strumento di terze parti. Non è garantito che funzioni per tutti i progetti e potrebbe causare lievi modifiche del comportamento di cui si dipende. CsprojToVs2017 deve essere usato come _punto iniziale_ che automatizza gli elementi di base che possono essere automatizzati. Non è una soluzione garantita per la migrazione dei formati di file di progetto.
