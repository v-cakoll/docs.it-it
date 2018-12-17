---
title: Librerie SourceLink e .NET
description: Procedure consigliate per l'uso di SourceLink per migliorare il debug per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128928"
---
# <a name="sourcelink"></a>SourceLink

SourceLink è una tecnologia che consente il debug del codice sorgente degli assembly .NET da NuGet da parte degli sviluppatori. SourceLink viene eseguito durante la creazione del pacchetto NuGet e incorpora i metadati di controllo dell'origine all'interno degli assembly e del pacchetto. Gli sviluppatori che scaricano il pacchetto e dispongono di SourceLink abilitato in Visual Studio possono eseguire l'istruzione del relativo codice sorgente. SourceLink fornisce i metadati di controllo dell'origine per creare una straordinaria esperienza di debug.

## <a name="sourcelink-demo"></a>Demo di SourceLink

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Uso di SourceLink

Le istruzioni per l'uso di SourceLink sono reperibili nel repository GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).

È possibile usare [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) per confermare che i metadati di SourceLink sono stati incorporati efficacemente nel pacchetto. Controllare che i metadati `Repository` siano presenti con un identificatore di commento e che i file con estensione .pdb si trovino insieme al .dll di ogni file di destinazione.

![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")

**✔️ VALUTARE** l'uso di SourceLink per aggiungere metadati di controllo del codice sorgente agli assembly e ai pacchetti NuGet.

> [!TIP]
> È possibile migliorare ulteriormente l'esperienza di debug di uno sviluppatore tramite l'aggiunta di attributi del debugger ai tipi in uso.
> * <xref:System.Diagnostics.DebuggerDisplayAttribute> può personalizzare la modalità di visualizzazione di una classe o di un campo nelle finestre delle variabili del debugger.
> * <xref:System.Diagnostics.DebuggerStepThroughAttribute> indica al debugger di eseguire il codice un'istruzione alla volta anziché eseguire un'istruzione nel codice.
> * <xref:System.Diagnostics.DebuggerBrowsableAttribute> controlla se viene visualizzato un membro nelle finestre delle variabili del debugger.

**✔️ VALUTARE** l'inclusione dei file di simboli (`*.pdb`) nel pacchetto NuGet principale.

> In genere, i file di simboli vengono pubblicati in un [pacchetto di simboli](./nuget.md#symbol-packages). Attualmente l'host pubblico principale per i pacchetti di simboli non supporta i file di simboli portatili (`*.pdb`) creati dai progetti in stile SDK e i pacchetti di simboli non sono utili.

>[!div class="step-by-step"]
>[Precedente](dependencies.md)
>[Successivo](publish-nuget-package.md)