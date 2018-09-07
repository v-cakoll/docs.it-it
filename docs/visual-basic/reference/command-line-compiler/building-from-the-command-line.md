---
title: Compilazione dalla riga di comando (Visual Basic)
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
ms.openlocfilehash: 89bcd6e0e7c1cc867bf853dc9bbe96628942ace2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078941"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilazione dalla riga di comando (Visual Basic)
Un progetto Visual Basic è costituito da uno o più file di origine separato. Durante il processo è noto come la compilazione, questi file vengono riuniti in un pacchetto, ovvero un singolo file eseguibile che può essere eseguito come un'applicazione.  
  
 Visual Basic fornisce un compilatore da riga di comando come alternativa alla compilazione dei programmi dall'interno l'ambiente di sviluppo integrato (IDE) di Visual Studio. Il compilatore della riga di comando è progettato per le situazioni in cui non richiedono il set completo di funzionalità nell'IDE, ad esempio, quando utilizzano o scrittura per i computer con spazio di archiviazione o memoria limitate sul sistema.  
  
  Per compilare i file di origine nell'IDE di Visual Studio, scegliere il **compilare** dalle **compilazione** menu.  
  
> [!TIP]
>  Quando si compila i file di progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sull'oggetto associato **vbc** comando e le opzioni nella finestra di output. Per visualizzare queste informazioni, aprire il [finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **livello di dettaglio output di compilazione progetto MSBuild** al **normale** o un livello di dettaglio maggiore. Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](https://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 È possibile compilare i file di progetto (con estensione vbproj) in un prompt dei comandi usando MSBuild. Per altre informazioni, vedere [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura:Richiamare il compilatore da riga di comando](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Viene descritto come richiamare il compilatore della riga di comando al prompt di MS-DOS o da una sottodirectory specifica.  
  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Fornisce un elenco di righe di comando di esempio che è possibile modificare per uso personale.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Fornisce elenchi di opzioni del compilatore, organizzati in ordine alfabetico o per utilizzo generico.  
  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Viene descritto come compilare determinate sezioni di codice.  
  
 [Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Compilazione e pulizia di progetti e soluzioni in Visual Studio)  
 Viene descritto come organizzare ciò che verrà incluso nella build diverse, scegliere le proprietà del progetto e assicurarsi che i progetti di compilazione nell'ordine corretto.
