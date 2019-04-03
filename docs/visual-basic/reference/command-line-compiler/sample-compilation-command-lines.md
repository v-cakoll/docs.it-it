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
ms.openlocfilehash: 0771ed41d6c58ce7cc98435b405f5819e45393db
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824304"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Righe di comando di esempio la compilazione (Visual Basic)
Come alternativa alla compilazione dei programmi Visual Basic dall'interno di Visual Studio, è possibile compilare dalla riga di comando per generare file di libreria a collegamento dinamico (DLL) o eseguibili (.exe).  
  
 Il compilatore della riga di comando di Visual Basic supporta un set completo di opzioni che controllano l'input e output i file, gli assembly e debug e le opzioni per il preprocessore. Ogni opzione è disponibile in due forme intercambiabili: `-option` e `/option`. Questa documentazione illustra solo la `-option` form.  
  
 La tabella seguente elenca alcune righe di comando di esempio che è possibile modificare per uso personale.  
  
|A|Usa|  
|--------|---------|  
|Compilare i file. vb e creare File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Compilare i file. vb e creare file. dll|`vbc -target:library File.vb`|  
|Compilare i file. vb e creare My.exe|`vbc -out:My.exe File.vb`|  
|Compilare i file. vb e creare una libreria sia un assembly di riferimento denominata file. dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Compilare tutti i file di Visual Basic nella directory corrente, con le ottimizzazioni in e `DEBUG` simbolo definito, generando File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Compilare tutti i file di Visual Basic nella directory corrente, generando una versione di debug di File2.dll senza visualizzare il logo o gli avvisi|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Compilare tutti i file di Visual Basic nella directory corrente in qualcosa. dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Quando si compila un progetto usando l'IDE di Visual Studio, è possibile visualizzare informazioni sull'oggetto associato **vbc** comando con le relative opzioni del compilatore nella finestra di output. Per visualizzare queste informazioni, aprire il [finestra di dialogo Opzioni, progetti e soluzioni, compila ed Esegui](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), quindi impostare il **livello di dettaglio output di compilazione progetto MSBuild** al **normale** o un livello di dettaglio maggiore.   
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
