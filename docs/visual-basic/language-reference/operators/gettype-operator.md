---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349556"
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
  
## <a name="remarks"></a>Osservazioni  
 L'operatore `GetType` restituisce l'oggetto <xref:System.Type> per la `typename`specificata. È possibile passare il nome di qualsiasi tipo definito in `typename`. Il comportamento predefinito include quanto segue:  
  
- Qualsiasi tipo di dati Visual Basic, ad esempio `Boolean` o `Date`.  
  
- Qualsiasi .NET Framework classe, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
- Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.  
  
- Qualsiasi matrice definita dall'applicazione.  
  
- Qualsiasi delegato definito dall'applicazione.  
  
- Qualsiasi enumerazione definita da Visual Basic, .NET Framework o dall'applicazione.  
  
 Se si desidera ottenere l'oggetto tipo di una variabile oggetto, utilizzare il metodo <xref:System.Type.GetType%2A?displayProperty=nameWithType>.  
  
 L'operatore `GetType` può essere utile nelle circostanze seguenti:  
  
- È necessario accedere ai metadati per un tipo in fase di esecuzione. L'oggetto <xref:System.Type> fornisce metadati, ad esempio i membri del tipo e le informazioni di distribuzione. Questa operazione è necessaria, ad esempio, per riflettere un assembly. Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo. In caso affermativo, `GetType` restituisce riferimenti allo stesso oggetto <xref:System.Type>.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene illustrato l'operatore `GetType` in uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
