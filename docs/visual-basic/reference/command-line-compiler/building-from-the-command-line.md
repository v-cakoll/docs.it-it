---
title: Compilazione dalla riga di comando
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: ec6ae3328c2042af950d1ee78a33d3de97219f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414298"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilazione dalla riga di comando (Visual Basic)

Un progetto Visual Basic è costituito da uno o più file di origine separati. Durante il processo noto come compilazione, questi file vengono raggruppati in un unico pacchetto, ovvero un singolo file eseguibile che può essere eseguito come applicazione.

Visual Basic fornisce un compilatore da riga di comando come alternativa alla compilazione di programmi dall'interno di Visual Studio Integrated Development Environment (IDE). Il compilatore da riga di comando è progettato per le situazioni in cui non è necessario il set completo di funzionalità nell'IDE, ad esempio quando si usa o si scrive per computer con memoria di sistema limitata o spazio di archiviazione.

Per compilare i file di origine dall'IDE di Visual Studio, scegliere il comando **Compila** dal menu **Compila** .

> [!TIP]
> Quando si compilano i file di progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sul comando **vbc** associato e sulle relative opzioni nella finestra output. Per visualizzare queste informazioni, aprire la finestra di [dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il livello di **dettaglio dell'output di compilazione del progetto MSBuild** su **normale** o su un livello di dettaglio superiore. Per altre informazioni, vedere [procedura: visualizzare, salvare e configurare i file di log di compilazione](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).

È possibile compilare file di progetto (con estensione vbproj) da un prompt dei comandi utilizzando MSBuild. Per altre informazioni, vedere Guida di [riferimento alla riga di comando](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).

## <a name="in-this-section"></a>Contenuto della sezione

[Procedura: richiamare il compilatore da riga di comando](how-to-invoke-the-command-line-compiler.md) \
Viene descritto come richiamare il compilatore da riga di comando al prompt di MS-DOS o da una sottodirectory specifica.

[Esempi di righe di comando di compilazione](sample-compilation-command-lines.md) \
Fornisce un elenco di righe di comando di esempio che è possibile modificare per uso personale.

## <a name="related-sections"></a>Sezioni correlate

[Visual Basic compilatore da riga di comando](index.md) \
Fornisce elenchi di opzioni del compilatore, organizzate in ordine alfabetico o per scopo.

[Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md) \
Viene descritto come compilare sezioni di codice specifiche.

[Compilazione e pulizia di progetti e soluzioni in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) \
Viene descritto come organizzare gli elementi che verranno inclusi in compilazioni diverse, scegliere le proprietà del progetto e assicurarsi che i progetti vengano compilati in base all'ordine corretto.
