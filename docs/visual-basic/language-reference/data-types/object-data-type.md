---
title: Object Data Type
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343958"
---
# <a name="object-data-type"></a>Object Data Type

Include indirizzi che fanno riferimento a oggetti. È possibile assegnare qualsiasi tipo di riferimento (stringa, matrice, classe o interfaccia) a una variabile `Object`. Una variabile `Object` può anche fare riferimento a dati di qualsiasi tipo di valore (numeric, `Boolean`, `Char`, `Date`, Structure o Enumeration).

## <a name="remarks"></a>Osservazioni

Il tipo di dati `Object` può puntare a dati di qualsiasi tipo di dati, incluse le istanze dell'oggetto riconosciute dall'applicazione. Utilizzare `Object` quando non è noto in fase di compilazione a quale tipo di dati può puntare la variabile.

Il valore predefinito di `Object` è `Nothing` (un riferimento null).

## <a name="data-types"></a>Tipi di dati

È possibile assegnare una variabile, una costante o un'espressione di qualsiasi tipo di dati a una variabile `Object`. Per determinare il tipo di dati a cui fa attualmente riferimento una variabile di `Object`, è possibile usare il metodo <xref:System.Type.GetTypeCode%2A> della classe <xref:System.Type?displayProperty=nameWithType>. Questa condizione è illustrata nell'esempio seguente.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

Il tipo di dati `Object` è un tipo di riferimento. Tuttavia, Visual Basic considera una variabile `Object` come tipo di valore quando fa riferimento ai dati di un tipo di valore.

## <a name="storage"></a>Archiviazione

Indipendentemente dal tipo di dati a cui fa riferimento, una variabile `Object` non contiene il valore di dati stesso, bensì un puntatore al valore. Usa sempre quattro byte nella memoria del computer, ma non include l'archiviazione per i dati che rappresentano il valore della variabile. A causa del codice che usa il puntatore per individuare i dati, `Object` variabili che tengono i tipi di valore sono leggermente più lente per l'accesso rispetto alle variabili tipizzate in modo esplicito.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con il tipo di `Object` Visual Basic.

- **Prestazioni.** Una variabile dichiarata con il tipo `Object` è sufficientemente flessibile da contenere un riferimento a qualsiasi oggetto. Tuttavia, quando si richiama un metodo o una proprietà in una variabile di questo tipo, si verifica sempre un' *associazione tardiva* (in fase di esecuzione). Per forzare l' *associazione anticipata* (in fase di compilazione) e migliorare le prestazioni, dichiarare la variabile con un nome di classe specifico oppure eseguirne il cast al tipo di dati specifico.

  Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifico, ad esempio <xref:System.OperatingSystem>, anziché il tipo di `Object` generalizzato. È inoltre consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> anziché <xref:System.Windows.Forms.Control>, in modo da poter accedere alle relative proprietà e metodi. In genere, è possibile usare l'elenco delle **classi** nella **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.

- **Conversioni.** Tutti i tipi di dati e tutti i tipi di riferimento vengono ampliati al tipo di dati `Object`. Ciò significa che è possibile convertire qualsiasi tipo in `Object` senza riscontrare un errore <xref:System.OverflowException?displayProperty=nameWithType>.

  Tuttavia, se si esegue la conversione tra *tipi di valore*e `Object`, Visual Basic esegue operazioni denominate *Boxing* e unboxing, che rendono l'esecuzione più lenta.

- **Digitare i caratteri.** `Object` non ha un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di Framework.** Il tipo corrispondente nella .NET Framework è la classe <xref:System.Object?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una variabile `Object` che punta a un'istanza dell'oggetto.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Procedura: determinare se due oggetti sono correlati](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedura: determinare se due oggetti sono identici](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
