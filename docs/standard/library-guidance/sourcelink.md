---
title: Librerie SourceLink e .NET
description: Procedure consigliate per l'uso di SourceLink per migliorare il debug per le librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: be97f868e2fcfc6c45e4bbac45b033f8914f4d99
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333538"
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

**✔️ VALUTARE** la pubblicazione dei file di simboli (`*.pdb`).

> Per altre informazioni sui file di simboli e i pacchetti di simboli, vedere [Pacchetti di simboli](./nuget.md#symbol-packages).

>[!div class="step-by-step"]
>[Precedente](dependencies.md)
>[Successivo](publish-nuget-package.md)
