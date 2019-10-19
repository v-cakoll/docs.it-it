---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 466bb5386235917705344d35c5141c8bf779218d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582639"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
Esistono due tipi di tipi in Visual Basic: tipi di riferimento e tipi di valore. Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati. Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile. Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su una variabile influiscano sull'altra (tranne nel caso del [modificatore ByRef nei parametri](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Tipi valore  
 Un tipo di dati è un *tipo di valore* se include i dati all'interno della propria allocazione di memoria. I tipi di valore includono i seguenti:  
  
- Tutti i tipi di dati numerici  
  
- `Boolean`, `Char`e `Date`  
  
- Tutte le strutture, anche se i relativi membri sono tipi di riferimento  
  
- Enumerazioni, poiché il tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` o `ULong`  
  
 Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento. Per questo motivo, i tipi di valore come `Char` e `Integer` vengono implementati da .NET Framework strutture.  
  
 È possibile dichiarare un tipo valore utilizzando la parola chiave riservata, ad esempio `Decimal`. È anche possibile usare la parola chiave `New` per inizializzare un tipo di valore. Questa operazione è particolarmente utile se il tipo dispone di un costruttore che accetta parametri. Un esempio è il costruttore <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, che compila un nuovo valore `Decimal` dalle parti fornite.  
  
## <a name="reference-types"></a>Tipi riferimento  
 Un *tipo riferimento* archivia un riferimento ai relativi dati. I tipi di riferimento includono gli elementi seguenti:  
  
- `String`  
  
- Tutte le matrici, anche se i relativi elementi sono tipi di valore  
  
- Tipi di classe, ad esempio <xref:System.Windows.Forms.Form>  
  
- Delegati  
  
 Una classe è un *tipo di riferimento*. Si noti che ogni matrice è un tipo di riferimento, anche se i relativi membri sono tipi valore.  
  
 Poiché ogni tipo di riferimento rappresenta una classe .NET Framework sottostante, è necessario utilizzare la parola chiave [new operator](../../../../visual-basic/language-reference/operators/new-operator.md) quando viene inizializzata. L'istruzione seguente Inizializza una matrice.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elementi che non sono tipi  
 Gli elementi di programmazione seguenti non sono qualificati come tipi, perché non è possibile specificarli come tipo di dati per un elemento dichiarato:  
  
- Namespaces  
  
- Moduli  
  
- eventi  
  
- Proprietà e procedure  
  
- Variabili, costanti e campi  
  
## <a name="working-with-the-object-data-type"></a>Utilizzo del tipo di dati Object  
 È possibile assegnare un tipo di riferimento o un tipo di valore a una variabile con il tipo di dati `Object`. Una variabile `Object` include sempre un riferimento ai dati, non i dati stessi. Tuttavia, se si assegna un tipo valore a una variabile di `Object`, si comporta come se contiene i propri dati. Per ulteriori informazioni, vedere [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 È possibile verificare se una variabile di `Object` funge da tipo di riferimento o un tipo di valore passandola al metodo <xref:Microsoft.VisualBasic.Information.IsReference%2A> nella classe <xref:Microsoft.VisualBasic.Information> dello spazio dei nomi <xref:Microsoft.VisualBasic?displayProperty=nameWithType>. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> restituisce `True` se il contenuto della variabile `Object` rappresenta un tipo di riferimento.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di valori nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Uso efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
