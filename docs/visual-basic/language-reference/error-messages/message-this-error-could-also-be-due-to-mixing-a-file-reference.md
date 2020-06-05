---
title: <message> Questo errore potrebbe essere dovuto anche all'unione di un riferimento file con un riferimento progetto nell'assembly '<assemblyname>'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 263e30f992ef58b0053acb2fd749d0d9186ef6b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397259"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>\<message> Questo errore potrebbe essere dovuto anche all'unione di un riferimento file con un riferimento progetto nell'assembly '\<assemblyname>'
\<message>Questo errore può essere dovuto anche alla combinazione di un riferimento di file con un riferimento di progetto all'assembly \<assemblyname> . In questo caso, provare a sostituire il riferimento file \<assemblyfilename> con '' nel progetto ' \<projectname1> ' con un riferimento al progetto a' \<projectname2> '.  
  
 Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non consente al compilatore Visual Basic di risolvere il riferimento.  
  
 Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve avere un riferimento a tale assembly. Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.  
  
 **ID errore:** BC30971  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento. Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.  
  
2. Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Risoluzione dei problemi relativi ai riferimenti interrotti](/visualstudio/ide/troubleshooting-broken-references)
