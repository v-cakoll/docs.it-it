---
title: Associazione anticipata e tardiva (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aceffe59fb6043b3089621b9a3f95b0425f9a522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="early-and-late-binding-visual-basic"></a>Associazione anticipata e tardiva (Visual Basic)
Quando un oggetto viene assegnato a una variabile oggetto, il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] esegue un processo denominato `binding`. Un oggetto è *ad associazione anticipata* quando viene assegnato a una variabile di un tipo object specifico. Gli oggetti ad associazione anticipata consentono al compilatore di allocare memoria ed effettuare altre ottimizzazioni prima dell'esecuzione di un'applicazione. Il frammento di codice seguente, ad esempio, dichiara una variabile di tipo <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 Poiché <xref:System.IO.FileStream> è un tipo object specifico, l'istanza assegnata a `FS` è ad associazione anticipata.  
  
 Al contrario, un oggetto è *ad associazione tardiva* quando viene assegnato a una variabile dichiarata di tipo `Object`. Gli oggetti di questo tipo possono contenere riferimenti a qualsiasi oggetto, ma non presentano molti dei vantaggi offerti dagli oggetti ad associazione anticipata. Il frammento di codice seguente, ad esempio, dichiara una variabile oggetto contenente un oggetto restituito dalla funzione `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a>Vantaggi offerti dall'associazione anticipata  
 Quando possibile, è consigliabile usare oggetti ad associazione anticipata. Tali oggetti consentono infatti al compilatore di eseguire ottimizzazioni significative che aumentano l'efficienza delle applicazioni. Gli oggetti ad associazione anticipata sono notevolmente più veloci di quelli ad associazione tardiva e facilitano la lettura e la gestione del codice dichiarando esattamente il tipo degli oggetti usati. Un altro vantaggio offerto dall'associazione anticipata è l'abilitazione di funzionalità utili quali il completamento automatico del codice e la Guida dinamica, perché l'ambiente di sviluppo integrato (IDE) [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] è in grado di determinare esattamente quale tipo di oggetto viene utilizzato durante la modifica del codice. L'associazione anticipata riduce il numero e la gravità degli errori di run-time poiché consente al compilatore di segnalare gli errori al momento della compilazione di un programma.  
  
> [!NOTE]
>  L'associazione tardiva può essere usata soltanto per accedere ai membri di tipi che vengono dichiarati come `Public`. L'accesso a membri dichiarati come `Friend` o `Protected Friend` determina un errore di run-time.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [Durata degli oggetti: come creare e distruggere oggetti](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
