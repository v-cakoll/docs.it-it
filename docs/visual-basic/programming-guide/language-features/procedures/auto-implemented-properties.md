---
title: Proprietà implementate automaticamente
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: b322bd2215c95298be0a33ace1f3590a63878e24
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350378"
---
# <a name="auto-implemented-properties-visual-basic"></a>Proprietà implementate automaticamente (Visual Basic)
*Auto-implemented properties* enable you to quickly specify a property of a class without having to write code to `Get` and `Set` the property. Quando si scrive il codice per una proprietà implementata automaticamente, il compilatore Visual Basic crea automaticamente un campo privato per archiviare la variabile della proprietà oltre a creare le routine `Get` e `Set` associate.  
  
 Con le proprietà implementate automaticamente, una proprietà, incluso un valore predefinito, può essere dichiarata in una sola riga. L'esempio seguente illustra tre dichiarazioni di proprietà.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 Una proprietà implementata automaticamente equivale a una proprietà il cui valore viene archiviato in un campo privato. L'esempio di codice seguente illustra una proprietà implementata automaticamente.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 L'esempio seguente illustra il codice equivalente per il precedente esempio di proprietà implementata automaticamente.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 Il codice seguente illustra l'implementazione delle proprietà di sola lettura:  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 È possibile assegnare alla proprietà con espressioni di inizializzazione, come illustrato nell'esempio, oppure nel costruttore del tipo contenitore.  È possibile assegnare ai campi sottostanti delle proprietà di sola lettura in qualsiasi momento.  
  
## <a name="backing-field"></a>Campo sottostante  
 When you declare an auto-implemented property, Visual Basic automatically creates a hidden private field called the *backing field* to contain the property value. Il nome del campo sottostante è il nome della proprietà implementata automaticamente preceduto da un carattere di sottolineatura (_). Ad esempio, se si dichiara una proprietà implementata automaticamente denominata `ID`, il campo sottostante viene denominato `_ID`. Se si include un membro della classe con il medesimo nome `_ID`, si produce un conflitto di denominazione e in Visual Basic viene segnalato un errore del compilatore.  
  
 Il campo sottostante presenta inoltre le caratteristiche seguenti:  
  
- Il modificatore di accesso per il campo sottostante è sempre `Private`, anche quando la proprietà stessa dispone di un livello di accesso diverso, ad esempio `Public`.  
  
- Se la proprietà è contrassegnata come `Shared`, anche il campo sottostante è condiviso.  
  
- Gli attributi specificati per la proprietà non si applicano al campo sottostante.  
  
- L'accesso al campo sottostante può essere eseguito dal codice all'interno della classe e dagli strumenti di debug, ad esempio la finestra Espressioni di controllo. Tuttavia, il campo sottostante non viene visualizzato in un elenco di completamento di parole di IntelliSense.  
  
## <a name="initializing-an-auto-implemented-property"></a>Inizializzazione di una proprietà implementata automaticamente  
 Qualsiasi espressione utilizzabile per inizializzare un campo è valida per l'inizializzazione di una proprietà implementata automaticamente. Quando si inizializza una proprietà implementata automaticamente, l'espressione viene valutata e passata alla routine `Set` per la proprietà. Gli esempi di codice seguenti mostrano alcune proprietà implementate automaticamente che includono i valori iniziali.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 Non è possibile inizializzare una proprietà implementata automaticamente che sia membro di un `Interface` o una che sia contrassegnata come `MustOverride`.  
  
 Quando si dichiara una proprietà implementata automaticamente come membro di una `Structure`, è possibile inizializzarla solo se è contrassegnata come `Shared`.  
  
 Quando si dichiara una proprietà implementata automaticamente come matrice, non è possibile specificare limiti di matrice espliciti. Tuttavia, si può specificare un valore usando un inizializzatore di matrice, come illustrato negli esempi seguenti.  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a>Definizioni di proprietà che richiedono la sintassi standard  
 Le proprietà implementate automaticamente sono semplici da usare e supportano molti scenari di programmazione. However, there are situations in which you cannot use an auto-implemented property and must instead use standard, or *expanded*, property syntax.  
  
 È necessario usare la sintassi di definizione della proprietà espansa se si vuole eseguire una delle operazioni seguenti:  
  
- Aggiungere codice alla routine `Get` o `Set` di una proprietà, ad esempio il codice per convalidare i valori in ingresso nella routine `Set`. È possibile, ad esempio, verificare che una stringa che rappresenta un numero di telefono contenga il numero obbligatorio di numerali prima di impostare il valore della proprietà.  
  
- Specificare un'accessibilità diversa per le routine `Get` e `Set`. Ad esempio, si può impostare la routine `Set` come `Private` e la routine `Get` come `Public`.  
  
- Creare proprietà `WriteOnly`.  
  
- Usare proprietà con parametri (incluse le proprietà `Default`). È necessario dichiarare una proprietà espansa per specificare un parametro per la proprietà o per specificare parametri aggiuntivi per la routine `Set`.  
  
- Inserire un attributo nel campo sottostante o modificare il livello di accesso del campo sottostante.  
  
- Fornire commenti XML per il campo sottostante.  
  
## <a name="expanding-an-auto-implemented-property"></a>Espansione di una proprietà implementata automaticamente  
 Se è necessario convertire una proprietà implementata automaticamente in una proprietà espansa contenente una routine `Get` o `Set`, l'editor di codice di Visual Basic può generare automaticamente le routine `Get` e `Set` e l'istruzione `End Property` per la proprietà. The code is generated if you put the cursor on a blank line following the `Property` statement, type a `G` (for `Get`) or an `S` (for `Set`) and press ENTER. L'editor di codice di Visual Basic genera automaticamente la routine `Get` o `Set` per le proprietà di sola lettura e di sola scrittura quando si preme INVIO alla fine di un'istruzione `Property`.  
  
## <a name="see-also"></a>Vedere anche

- [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)
- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
