---
title: 'Procedura: Convertire un oggetto in un altro tipo'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393961"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Procedura: convertire un oggetto in un altro tipo in Visual Basic
Per convertire una `Object` variabile in un altro tipo di dati, è possibile utilizzare una parola chiave di conversione come la [funzione CType](../../../language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene convertita una `Object` variabile in un oggetto `Integer` e un oggetto `String` .  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Se si sa che il contenuto di una `Object` variabile è di un determinato tipo di dati, è preferibile convertire la variabile in quel tipo di dati. Se si continua a usare la `Object` variabile, è necessario eseguire la *conversione boxing* e *unboxing* (per un tipo di valore) o l' *associazione tardiva* (per un tipo di riferimento). Queste operazioni consentono di ottenere tempo di esecuzione aggiuntivo e rallentare le prestazioni.  
  
## <a name="compile-the-code"></a>Compilare il codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object>
- [Conversioni di tipi in Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](implicit-and-explicit-conversions.md)
- [Conversioni fra stringhe e altri tipi](conversions-between-strings-and-other-types.md)
- [Conversioni di matrice](array-conversions.md)
- [Strutture](structures.md)
- [Tipi di dati](../../../language-reference/data-types/index.md)
- [CString](../../../language-reference/functions/type-conversion-functions.md)
