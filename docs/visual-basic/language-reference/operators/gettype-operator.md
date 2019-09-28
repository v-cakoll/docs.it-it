---
title: Operatore GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592158"
---
# <a name="gettype-operator-visual-basic"></a>Operatore GetType (Visual Basic)
Restituisce un oggetto <xref:System.Type> per il tipo specificato. L'oggetto <xref:System.Type> fornisce informazioni sul tipo, ad esempio proprietà, metodi ed eventi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`typename`|Nome del tipo per il quale si desiderano le informazioni.|  
  
## <a name="remarks"></a>Note  
 L'operatore `GetType` restituisce l'oggetto <xref:System.Type> per il `typename` specificato. È possibile passare il nome di qualsiasi tipo definito in `typename`. Sono inclusi gli elementi seguenti:  
  
- Qualsiasi tipo di dati Visual Basic, ad esempio `Boolean` o `Date`.  
  
- Qualsiasi .NET Framework classe, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
- Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.  
  
- Qualsiasi matrice definita dall'applicazione.  
  
- Qualsiasi delegato definito dall'applicazione.  
  
- Qualsiasi enumerazione definita da Visual Basic, .NET Framework o dall'applicazione.  
  
 Se si desidera ottenere l'oggetto tipo di una variabile oggetto, utilizzare il metodo <xref:System.Type.GetType%2A?displayProperty=nameWithType>.  
  
 L'operatore `GetType` può essere utile nelle circostanze seguenti:  
  
- È necessario accedere ai metadati per un tipo in fase di esecuzione. L'oggetto <xref:System.Type> fornisce i metadati, ad esempio i membri del tipo e le informazioni di distribuzione. Questa operazione è necessaria, ad esempio, per riflettere un assembly. Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo. In tal caso, `GetType` restituisce riferimenti allo stesso oggetto <xref:System.Type>.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene illustrato l'operatore `GetType` in uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
