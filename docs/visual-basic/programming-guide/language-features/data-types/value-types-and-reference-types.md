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
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504886"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
Esistono due tipi di tipi in Visual Basic: fare riferimento a tipi e i tipi di valore. Le variabili dei tipi di riferimento archiviano i riferimenti ai relativi dati (oggetti), mentre le variabili dei tipi di valore contengono direttamente i dati. Con i tipi di riferimento, due variabili possono fare riferimento allo stesso oggetto. Di conseguenza le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra variabile. Tipi di valore, ogni variabile ha una propria copia dei dati e non è possibile per operazioni su una variabile influiscano su altra (tranne nel caso del [modificatore ByRef sui parametri](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Tipi valore  
 Un tipo di dati è un *tipo di valore* se contiene i dati nella propria allocazione di memoria. I tipi di valore seguenti:  
  
- Tutti i tipi di dati numerici  
  
- `Boolean`, `Char`e `Date`  
  
- Tutte le strutture, anche se i relativi membri sono i tipi di riferimento  
  
- Le enumerazioni, in quanto il relativo tipo sottostante è sempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o `ULong`  
  
 Ogni struttura è un tipo valore, anche se contiene membri di tipo riferimento. Per questo motivo, i tipi valore, ad esempio `Char` e `Integer` vengono implementate dalle strutture .NET Framework.  
  
 È possibile dichiarare un tipo di valore usando la parola chiave riservata, ad esempio, `Decimal`. È anche possibile usare il `New` (parola chiave) per inizializzare un tipo di valore. Ciò è particolarmente utile se il tipo ha un costruttore che accetta parametri. Un esempio di questo è il <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> costruttore, che crea un nuovo `Decimal` valore dalle parti fornite.  
  
## <a name="reference-types"></a>Tipi riferimento  
 Oggetto *fanno riferimento a tipo* archivia un riferimento ai relativi dati. I tipi di riferimento includono quanto segue:  
  
- `String`  
  
- Tutte le matrici, anche se i relativi elementi sono tipi valore  
  
- Tipi di classe, ad esempio <xref:System.Windows.Forms.Form>  
  
- Delegati  
  
 Una classe è un *fanno riferimento a tipo*. Si noti che ogni matrice è un tipo riferimento, anche se i relativi membri sono tipi valore.  
  
 Poiché ogni tipo di riferimento rappresenta una classe sottostante di .NET Framework, è necessario usare il [operatore New](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave quando si inizializza. L'istruzione seguente consente di inizializzare una matrice.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elementi che non sono tipi  
 Gli elementi di programmazione seguenti non sono idonei come tipi, poiché non è possibile specificare uno di essi come tipo di dati per un elemento dichiarato:  
  
- Spazi dei nomi  
  
- Moduli  
  
- Eventi  
  
- Proprietà e routine  
  
- Le variabili, costanti e i campi  
  
## <a name="working-with-the-object-data-type"></a>Utilizzo l'oggetto tipo di dati  
 È possibile assegnare un tipo riferimento o un tipo di valore a una variabile del `Object` tipo di dati. Un `Object` variabile contiene sempre un riferimento ai dati, mai i dati stessi. Tuttavia, se si assegna un tipo di valore a un `Object` variabile, si comporta come se contenesse i propri dati. Per altre informazioni, vedere [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 È possibile stabilire se un' `Object` variabile funge da un tipo riferimento o un tipo di valore passandolo al <xref:Microsoft.VisualBasic.Information.IsReference%2A> metodo nella <xref:Microsoft.VisualBasic.Information> classe del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> dello spazio dei nomi. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Restituisce `True` se il contenuto di `Object` variabile rappresenta un tipo di riferimento.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di valori nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Uso efficiente dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
