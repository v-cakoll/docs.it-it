---
title: Metodi System.Convert
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: c3b8c7105578c57547b79bc95b633bcc6449a0ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591717"
---
# <a name="systemconvert-methods"></a>Metodi System.Convert
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non sono supportati i metodi <xref:System.Convert> riportati di seguito.  
  
-   Versioni con un parametro <xref:System.IFormatProvider>.  
  
-   Metodi che interessano matrici di caratteri o matrici di byte:  
  
    -   <xref:System.Convert.FromBase64CharArray%2A>  
  
    -   <xref:System.Convert.ToBase64CharArray%2A>  
  
    -   <xref:System.Convert.FromBase64String%2A>  
  
    -   <xref:System.Convert.ToBase64String%2A>  
  
-   I seguenti metodi:  
  
    -   `public static <Type2> To<Type2>(<Type1> value);` dove  
  
         `Type1` e `Type2` corrispondono ognuno a `sbyte`, `uint`, `ulong` o `ushort`.  
  
    -   C#:  
  
         `int To<int type>(string value, int fromBase),`  
  
         `ToString(... value, int toBase)`  
  
    -   Visual Basic:  
  
         `Function To(Of [Numeric])(value as String, fromBase As Integer)`  
  
         `As [Numeric], ToString( value As …, toBase As Integer)`  
  
    -   <xref:System.Convert.IsDBNull%2A>  
  
    -   <xref:System.Convert.GetTypeCode%2A>  
  
    -   <xref:System.Convert.ChangeType%2A>  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
