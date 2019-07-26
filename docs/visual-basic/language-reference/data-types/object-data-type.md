---
title: Tipo di dati Object (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513054"
---
# <a name="object-data-type"></a>Object Data Type

Include indirizzi che fanno riferimento a oggetti. È possibile assegnare qualsiasi tipo di riferimento (stringa, matrice, classe o interfaccia) a una `Object` variabile. Una `Object` variabile può anche fare riferimento a dati di qualsiasi tipo di valore ( `Boolean`numeric `Char`, `Date`,,, Structure o Enumeration).

## <a name="remarks"></a>Note

Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, inclusa qualsiasi istanza di oggetto riconosciuta dall'applicazione. Usare `Object` quando non si conosce in fase di compilazione a quale tipo di dati può puntare la variabile.

Il valore predefinito di `Object` è `Nothing` (un riferimento null).

## <a name="data-types"></a>Tipi di dati

È possibile assegnare una variabile, una costante o un'espressione di qualsiasi tipo di dati `Object` a una variabile. Per determinare il tipo di dati `Object` a cui fa attualmente riferimento una variabile, è <xref:System.Type.GetTypeCode%2A> possibile usare il <xref:System.Type?displayProperty=nameWithType> metodo della classe. Questa condizione è illustrata nell'esempio seguente.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Il `Object` tipo di dati è un tipo di riferimento. Tuttavia, Visual Basic considera una `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo di valore.

## <a name="storage"></a>Archiviazione

Indipendentemente dal tipo di dati a cui `Object` fa riferimento, una variabile non contiene il valore di dati stesso, bensì un puntatore al valore. Usa sempre quattro byte nella memoria del computer, ma non include l'archiviazione per i dati che rappresentano il valore della variabile. A causa del codice che usa il puntatore per individuare i dati, `Object` le variabili che mantengono i tipi di valore sono leggermente più lente per accedere alle variabili tipizzate in modo esplicito.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti com o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con il `Object` tipo di Visual Basic.

- **Prestazioni.** Una variabile dichiarata con `Object` il tipo è sufficientemente flessibile da contenere un riferimento a qualsiasi oggetto. Tuttavia, quando si richiama un metodo o una proprietà in una variabile di questo tipo, si verifica sempre un' *associazione tardiva* (in fase di esecuzione). Per forzare l' *associazione anticipata* (in fase di compilazione) e migliorare le prestazioni, dichiarare la variabile con un nome di classe specifico oppure eseguirne il cast al tipo di dati specifico.

  Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifico, ad <xref:System.OperatingSystem>esempio, anziché il `Object` tipo generalizzato. È inoltre consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control>anziché, in modo da poter accedere alle proprietà e ai metodi. In genere, è possibile usare l'elenco delle **classi** nella **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.

- **Conversioni.** Tutti i tipi di dati e tutti i tipi di `Object` riferimento vengono ampliati al tipo di dati. Ciò significa che è possibile convertire qualsiasi tipo `Object` in senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.

  Tuttavia, se si esegue la conversione tra tipi `Object`di valore e, Visual Basic esegue operazioni denominate *Boxing* *e unboxing*, che rendono l'esecuzione più lenta.

- **Digitare i caratteri.** `Object`non ha un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di Framework.** Il tipo corrispondente nella .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata `Object` una variabile che punta a un'istanza dell'oggetto.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Procedura: Determinare se due oggetti sono correlati](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedura: Determinare se due oggetti sono identici](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
