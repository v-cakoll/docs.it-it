---
title: "&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento al file con un riferimento progetto all'assembly &#39; &lt;assemblyname&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 498ca74497077e3268aa8cb25ce5121f3c9ea59d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588337"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento al file con un riferimento progetto all'assembly &#39; &lt;assemblyname&gt;&#39;
\<messaggio > Questo errore potrebbe anche essere dovuta alla combinazione di un riferimento al file con un riferimento progetto all'assembly '\<NomeAssembly >. In questo caso, provare a sostituire il riferimento file a '\<assemblyfilename >' nel progetto '\<nomeprogetto1 >' con un riferimento al progetto '\<nomeprogetto2 >'.  
  
 Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non consente il compilatore Visual Basic risolvere il riferimento.  
  
 Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve includere un riferimento a tale assembly. Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.  
  
 **ID errore:** BC30971  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento. Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.  
  
2.  Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
