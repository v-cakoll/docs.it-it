---
title: Tipo di dati definito dall'utente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 1dac93145b6e11a0d149f03b43e1e0b28b770925
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45509844"
---
# <a name="user-defined-data-type"></a>Tipo di dati definito dall'utente
Contiene i dati in un formato definito. Il `Structure` istruzione definisce il formato.  
  
 Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT). La versione corrente lo espande in un *struttura*. Una struttura è una concatenazione di una o più *membri* di vari tipi di dati. Visual Basic vengono considerati una struttura di una singola unità, anche se è anche possibile accedere singolarmente i relativi membri.  
  
## <a name="remarks"></a>Note  
 Definire e usare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità, o quando nessuno dei tipi di dati elementari soddisfare le esigenze.  
  
 Il valore predefinito di un tipo di dati di struttura è costituito dalla combinazione dei valori predefiniti della ognuno dei relativi membri.  
  
## <a name="declaration-format"></a>Formato di dichiarazione  
 Una dichiarazione structure inizia con la [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) e termina con il `End Structure` istruzione. Il `Structure` istruzione fornisce il nome della struttura, che è anche l'identificatore del tipo di dati consente di definire la struttura. Altre parti del codice è possono usare questo identificatore per dichiarare variabili, parametri e funzioni restituiscono valori di tipo di dati della struttura.  
  
 Le dichiarazioni tra il `Structure` e `End Structure` istruzioni definiscano i membri della struttura.  
  
## <a name="member-access-levels"></a>Livelli di accesso di membro  
 È necessario dichiarare ogni membro usando un [istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [pubblico](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privato](../../../visual-basic/language-reference/modifiers/private.md). Se si usa un `Dim` informativa, le impostazioni predefinite a livello di accesso su pubblico.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Utilizzo di memoria.** Come con tutti i tipi di dati compositi, è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura sommando le allocazioni di archiviazione nominale dei relativi membri. Inoltre, non è possibile tranquillamente presupporre che l'ordine di archiviazione in memoria è lo stesso l'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> dell'attributo di `Structure` istruzione.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic i tipi di struttura.  
  
-   **Ampliamento.** Non vi è alcuna conversione automatica a o da qualsiasi tipo di dati della struttura. È possibile definire operatori di conversione per la struttura tramite il [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md), è possibile dichiarare ogni operatore di conversione sia `Widening` o `Narrowing`.  
  
-   **Caratteri tipo.** Tipi di dati di struttura non dispongono di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** È disponibile alcun tipo corrispondente in .NET Framework. Tutte le strutture ereditano dalla classe di .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, ma nessun singole strutture corrisponde a <xref:System.ValueType?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Il paradigma comune della seguente viene illustrata la struttura della dichiarazione di una struttura.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
