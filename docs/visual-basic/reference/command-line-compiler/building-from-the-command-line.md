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
ms.openlocfilehash: 391e16da86aa741a1b78f35d9afd95688f33c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654135"
---
# <a name="building-from-the-command-line-visual-basic"></a>Compilazione dalla riga di comando (Visual Basic)
Un progetto Visual Basic è costituito da uno o più file di origine distinta. Durante il processo è noto come compilazione, questi file vengono riuniti in un pacchetto, ovvero un singolo file eseguibile che può essere eseguito come un'applicazione.  
  
 Visual Basic fornisce un compilatore da riga di comando come alternativa alla compilazione dei programmi dall'interno l'ambiente di sviluppo integrato (IDE) di Visual Studio. Il compilatore della riga di comando è progettato per situazioni che non richiedono il set completo di funzionalità nell'IDE, ad esempio, quando utilizzano o scrittura per i computer con sistema limitato della memoria o spazio di archiviazione.  
  
  Per compilare file di origine dall'IDE di Visual Studio, scegliere il **compilare** comando il **compilare** menu.  
  
> [!TIP]
>  Quando si compila i file di progetto tramite l'IDE di Visual Studio, è possibile visualizzare informazioni su associato **vbc** comando e le opzioni nella finestra di output. Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio. Per altre informazioni, vedere [Procedura: Visualizzare, salvare e configurare file di log di compilazione](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).  
  
 È possibile compilare i file di progetto (con estensione vbproj) in un prompt dei comandi tramite MSBuild. Per ulteriori informazioni, vedere [riferimento della riga di comando](/visualstudio/msbuild/msbuild-command-line-reference) e [procedura dettagliata: uso di MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura:Richiamare il compilatore da riga di comando](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Viene descritto come richiamare il compilatore della riga di comando al prompt di MS-DOS o da una sottodirectory specifica.  
  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Fornisce un elenco delle righe di comando di esempio che è possibile modificare le proprie esigenze.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 Vengono forniti elenchi di opzioni del compilatore, organizzati in ordine alfabetico in base allo scopo.  
  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Viene descritto come compilare particolari sezioni di codice.  
  
 [Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Compilazione e pulizia di progetti e soluzioni in Visual Studio)  
 Viene descritto come organizzare gli elementi verranno inclusi nelle compilazioni diverse, scegliere le proprietà del progetto e generare i progetti nell'ordine corretto.
