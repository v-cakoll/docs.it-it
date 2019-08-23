---
title: Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 0683047865f520a09b2d2fe196096286b7d78714
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965388"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)
Nella maggior parte dei casi, è possibile individuare le proprietà e i metodi di un oggetto in fase di progettazione e scrivere codice per gestirli. Tuttavia, in alcuni casi è possibile che non si conoscano le proprietà e i metodi di un oggetto in anticipo oppure è possibile che si voglia solo la flessibilità di consentire a un utente finale di specificare le proprietà o eseguire metodi in fase di esecuzione.  
  
## <a name="callbyname-function"></a>CallByName (funzione)  
 Si consideri, ad esempio, un'applicazione client che valuta le espressioni immesse dall'utente passando un operatore a un componente COM. Si supponga di aggiungere continuamente nuove funzioni al componente che richiedono nuovi operatori. Quando si utilizzano le tecniche standard di accesso agli oggetti, è necessario ricompilare e ridistribuire l'applicazione client prima di poter utilizzare i nuovi operatori. Per evitare questo problema, è possibile usare `CallByName` la funzione per passare i nuovi operatori come stringhe, senza modificare l'applicazione.  
  
 La `CallByName` funzione consente di usare una stringa per specificare una proprietà o un metodo in fase di esecuzione. La firma per la `CallByName` funzione è simile alla seguente:  
  
 *Risultato*(Object, ProcedureName, CallType, Arguments ()) = `CallByName`  
  
 Il primo argomento, *Object*, accetta il nome dell'oggetto su cui si vuole agire. L' argomento ProcedureName accetta una stringa che contiene il nome del metodo o della routine della proprietà da richiamare. L'argomento *CallType* accetta una costante che rappresenta il tipo di procedura da richiamare, ovvero un metodo`Microsoft.VisualBasic.CallType.Method`(), una proprietà Read`Microsoft.VisualBasic.CallType.Get`() o un set di proprietà`Microsoft.VisualBasic.CallType.Set`(). L' argomento arguments, che è facoltativo, accetta una matrice di `Object` tipo che contiene gli argomenti della routine.  
  
 È possibile usare `CallByName` con le classi nella soluzione corrente, ma viene usato più spesso per accedere a oggetti o oggetti com da .NET Framework assembly.  
  
 Si supponga di aggiungere un riferimento a un assembly che contiene una classe `MathClass`denominata, con una nuova funzione denominata `SquareRoot`, come illustrato nel codice seguente:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 L'applicazione può usare i controlli casella di testo per controllare il metodo che verrà chiamato e i relativi argomenti. Se `TextBox1` , ad esempio, contiene l'espressione da valutare e `TextBox2` viene utilizzata per immettere il nome della funzione, è possibile utilizzare il codice seguente per richiamare la `SquareRoot` funzione nell'espressione in `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 Se si immette "64" in `TextBox1`, "SquareRoot" in `TextBox2`e quindi si chiama la `CallMath` routine, viene valutata la radice quadrata `TextBox1` del numero in. Il codice nell'esempio richiama la `SquareRoot` funzione (che accetta una stringa che contiene l'espressione da valutare come argomento obbligatorio) e restituisce "8" in `TextBox1` (la radice quadrata di 64). Naturalmente, se l'utente immette una stringa non valida in `TextBox2`, se la stringa contiene il nome di una proprietà anziché un metodo o se il metodo ha un argomento obbligatorio aggiuntivo, si verificherà un errore di run-time. È necessario aggiungere un codice di gestione degli errori affidabile quando si `CallByName` USA per prevedere questi o altri errori.  
  
> [!NOTE]
> Sebbene la `CallByName` funzione possa risultare utile in alcuni casi, è necessario ponderarne l'utilità rispetto alle implicazioni relative alle `CallByName` prestazioni, ovvero l'utilizzo di per richiamare una stored procedure è leggermente più lento rispetto a una chiamata ad associazione tardiva. Se si richiama una funzione che viene chiamata ripetutamente, ad esempio all'interno di un ciclo `CallByName` , può avere un effetto grave sulle prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Determinazione del tipo di un oggetto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
