---
title: Esempi di righe di comando di compilazione (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0f1fc1d269801efdbf2e89d10679dc8159851f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Esempi di righe di comando compilazione (Visual Basic)
Come alternativa alla compilazione dei programmi Visual Basic da Visual Studio, è possibile compilare dalla riga di comando per generare file di libreria a collegamento dinamico (DLL) o file eseguibile (.exe).  
  
 Il compilatore della riga di comando di Visual Basic supporta un set completo di opzioni che controllano l'input e output di file, gli assembly, debug e le opzioni per il preprocessore. Ogni opzione è disponibile in due formati intercambiabili: `-option` e `/option`. Questa documentazione viene visualizzato soltanto il `-option` form.  
  
 Nella tabella seguente sono elencati alcuni esempi di righe di comando che è possibile modificare le proprie esigenze.  
  
|A|Usa|  
|--------|---------|  
|Compilare i file. vb e creare File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilare i file. vb e creare file. dll|`vbc -target:library File.vb`|  
|Compilare i file. vb e creare My.exe|`vbc -out:My.exe File.vb`|  
|Compilare i file. vb e creare una libreria sia un assembly di riferimento denominata DLL|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilare tutti i file di Visual Basic nella directory corrente, con le ottimizzazioni in e `DEBUG` simbolo definito, generando File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Compilare tutti i file di Visual Basic nella directory corrente, generando una versione di debug di File2 senza visualizzare il logo o gli avvisi|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Compilare tutti i file di Visual Basic nella directory corrente in qualcosa. dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Quando si compila un progetto tramite l'IDE di Visual Studio, è possibile visualizzare informazioni su associato **vbc** comando con le opzioni del compilatore nella finestra di output. Per visualizzare queste informazioni, aprire il [la finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **dettaglio di output di compilazione progetto MSBuild** a **normale** o un livello di dettaglio.   
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
