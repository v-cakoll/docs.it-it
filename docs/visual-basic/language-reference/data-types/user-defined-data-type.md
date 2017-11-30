---
title: Tipo di dati definito dall'utente
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a>Tipo di dati definito dall'utente
Contiene i dati in un formato definito. Il `Structure` istruzione definisce il formato.  
  
 Le versioni precedenti di Visual Basic supportano il tipo definito dall'utente (UDT). La versione corrente lo espande in un *struttura*. Una struttura è una concatenazione di uno o più *membri* vari tipi di dati. Viene considerata una struttura di una singola unità, anche se è inoltre possibile accedere singolarmente i relativi membri.  
  
## <a name="remarks"></a>Note  
 Definire e utilizzare un tipo di dati di struttura quando è necessario combinare diversi tipi di dati in una singola unità, o quando nessuno dei tipi di dati elementare servire le proprie esigenze.  
  
 Il valore predefinito di un tipo di dati di struttura è costituito dalla combinazione dei valori predefiniti di ognuno dei relativi membri.  
  
## <a name="declaration-format"></a>Formato di dichiarazione  
 Una dichiarazione di struttura inizia con il [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) e termina con il `End``Structure` istruzione. Il `Structure` istruzione fornisce il nome della struttura, che è anche l'identificatore del tipo di dati consiste nel definire la struttura. Altre parti del codice è possono utilizzare questo identificatore per dichiarare le variabili, parametri e funzione di restituire i valori per questo tipo di struttura dati.  
  
 Le dichiarazioni tra il `Structure` e `End``Structure` istruzioni definiscano i membri della struttura.  
  
## <a name="member-access-levels"></a>Livelli di accesso di membro  
 È necessario dichiarare ogni membro utilizzando un [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md) o un'istruzione che specifica il livello di accesso, ad esempio [pubblica](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), o [privato](../../../visual-basic/language-reference/modifiers/private.md). Se si utilizza un `Dim` istruzione, impostazioni predefinite a livello di accesso al ruolo public.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Utilizzo di memoria.** Come con tutti i tipi di dati compositi, è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura sommando le allocazioni di memoria nominali dei relativi membri. Inoltre, non è possibile presupporre che l'ordine di archiviazione in memoria è identico all'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo la `Structure` istruzione.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi definiti dall'utente in altri ambienti non sono compatibili con Visual Basic i tipi di struttura.  
  
-   **Ampliamento.** Non è una conversione automatica a o da qualsiasi tipo di dati della struttura. È possibile definire gli operatori di conversione per la struttura utilizzando il [Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md), ed è possibile dichiarare ogni operatore di conversione da `Widening` o `Narrowing`.  
  
-   **Caratteri tipo.** Tipi di dati di struttura non dispongono di alcun carattere di tipo letterale o un carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Non vi è alcun tipo corrispondente in .NET Framework. Tutte le strutture ereditano dalla classe di .NET Framework <xref:System.ValueType?displayProperty=nameWithType>, ma nessuna struttura singola corrisponde a <xref:System.ValueType?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio che segue viene illustrata la struttura della dichiarazione di una struttura.  
  
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
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
