---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 37644a9c37ffde084120c5f1e1ee8c87a04ffc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371155"
---
# <a name="gettype-operator-visual-basic"></a>Operatore GetType (Visual Basic)
Restituisce un <xref:System.Type> oggetto per il tipo specificato. L' <xref:System.Type> oggetto fornisce informazioni sul tipo, ad esempio proprietà, metodi ed eventi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`typename`|Nome del tipo per il quale si desiderano le informazioni.|  
  
## <a name="remarks"></a>Commenti  
 L' `GetType` operatore restituisce l' <xref:System.Type> oggetto per l'oggetto specificato `typename` . È possibile passare il nome di qualsiasi tipo definito in `typename` . Sono inclusi gli elementi seguenti:  
  
- Qualsiasi tipo di dati Visual Basic, ad esempio `Boolean` o `Date` .  
  
- Qualsiasi .NET Framework classe, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType> .  
  
- Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.  
  
- Qualsiasi matrice definita dall'applicazione.  
  
- Qualsiasi delegato definito dall'applicazione.  
  
- Qualsiasi enumerazione definita da Visual Basic, .NET Framework o dall'applicazione.  
  
 Se si desidera ottenere l'oggetto tipo di una variabile oggetto, utilizzare il <xref:System.Type.GetType%2A?displayProperty=nameWithType> metodo.  
  
 L' `GetType` operatore può essere utile nelle circostanze seguenti:  
  
- È necessario accedere ai metadati per un tipo in fase di esecuzione. L' <xref:System.Type> oggetto fornisce metadati quali i membri del tipo e le informazioni sulla distribuzione. Questa operazione è necessaria, ad esempio, per riflettere un assembly. Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo. In caso affermativo, `GetType` restituisce riferimenti allo stesso <xref:System.Type> oggetto.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene illustrato l' `GetType` operatore in uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
