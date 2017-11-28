---
title: "Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5974257fb82fe83c66a480225da200c14338898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)
Nella maggior parte dei casi, è possibile individuare le proprietà e metodi di un oggetto in fase di progettazione e scrivere codice per gestirli. Tuttavia, in alcuni casi potrebbe non sapere sulle proprietà e metodi di un oggetto in anticipo, o si potrebbe volere la flessibilità di un utente finale di specificare le proprietà o eseguire i metodi in fase di esecuzione.  
  
## <a name="callbyname-function"></a>CallByName (funzione)  
 Si consideri, ad esempio, un'applicazione client che valuta espressioni immesse dall'utente tramite il passaggio di un operatore di un componente COM. Si supponga che si siano aggiungendo nuove funzioni costantemente il componente che richiedono nuovi operatori. Quando si utilizzano tecniche di accesso agli oggetti standard, è necessario ricompilare e ridistribuire l'applicazione client prima che è possibile usare i nuovi operatori. Per evitare questo problema, è possibile utilizzare il `CallByName` funzione per passare i nuovi operatori come stringhe, senza modificare l'applicazione.  
  
 Il `CallByName` funzione consente di utilizzare una stringa per specificare una proprietà o metodo in fase di esecuzione. La firma per il `CallByName` funzione è simile al seguente:  
  
 *Risultato* = `CallByName`(*oggetto*, *nomeroutine*, *CallType*, *argomenti*())  
  
 Il primo argomento, *oggetto*, accetta il nome dell'oggetto a cui si desidera agire. Il *nomeroutine* argomento accetta una stringa che contiene il nome del metodo o proprietà della routine da richiamare. Il *CallType* argomento accetta una costante che rappresenta il tipo di routine da richiamare: un metodo (`Microsoft.VisualBasic.CallType.Method`), una proprietà di lettura (`Microsoft.VisualBasic.CallType.Get`), o una proprietà impostata (`Microsoft.VisualBasic.CallType.Set`). Il *argomenti* argomento è facoltativo, prende una matrice di tipo `Object` che contiene gli argomenti per la procedura.  
  
 È possibile utilizzare `CallByName` con le classi nella soluzione corrente, ma vengono spesso usati per accedere agli oggetti COM o oggetti da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly.  
  
 Si supponga di aggiunta un riferimento a un assembly che contiene una classe denominata `MathClass`, che dispone di una nuova funzione denominata `SquareRoot`, come illustrato nel codice seguente:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 L'applicazione è possibile utilizzare controlli casella di testo al controllo verrà chiamato il metodo e i relativi argomenti. Ad esempio, se `TextBox1` contiene l'espressione da valutare e `TextBox2` viene utilizzata per immettere il nome della funzione, è possibile utilizzare il codice seguente per richiamare il `SquareRoot` funzione nell'espressione nel `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Se si immette "64" in `TextBox1`, "SquareRoot" in `TextBox2`e quindi chiamare il `CallMath` procedure, la radice quadrata del numero in `TextBox1` viene valutata. Il codice di esempio richiama il `SquareRoot` funzione (che accetta una stringa che contiene l'espressione da valutare come un argomento obbligatorio) e restituisce "8" `TextBox1` (la radice quadrata di 64). Naturalmente, se l'utente immette una stringa non valida in `TextBox2`, se la stringa contenente il nome di una proprietà anziché un metodo, o se il metodo richiede un argomento aggiuntivo, si verifica un errore di run-time. È necessario aggiungere codice di gestione degli errori affidabile quando si utilizza `CallByName` per prevenire questo o altri errori.  
  
> [!NOTE]
>  Mentre il `CallByName` può risultare utile in alcuni casi, è necessario valutare dell'utilità, anche le implicazioni sulle prestazioni, utilizzando `CallByName` per richiamare una stored procedure è leggermente più lento rispetto a una chiamata ad associazione tardiva. Se si sta chiamando una funzione chiamata più volte, ad esempio all'interno di un ciclo, `CallByName` può avere un grave impatto sulle prestazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [Determinazione del tipo di un oggetto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
