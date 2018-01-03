---
title: '&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento a file e un riferimento progetto all''assembly &#39;&lt; AssemblyName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0fcbcc48928b1b03487f31930e3d14051ddd990a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento a file e un riferimento progetto all'assembly &#39;&lt; AssemblyName&gt;&#39;
\<messaggio > Questo errore potrebbe anche essere dovuta alla combinazione di un riferimento al file con un riferimento progetto all'assembly '\<NomeAssembly >. In questo caso, provare a sostituire il riferimento file a '\<assemblyfilename >' nel progetto '\<nomeprogetto1 >' con un riferimento al progetto '\<nomeprogetto2 >'.  
  
 Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non permette al compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per risolvere il riferimento.  
  
 Per accedere a un tipo definito in un altro assembly, il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve avere un riferimento a quell'assembly. Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.  
  
 **ID errore:** BC30971  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento. Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.  
  
2.  Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
