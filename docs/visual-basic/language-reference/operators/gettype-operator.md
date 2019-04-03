---
title: Operatore GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840321"
---
# <a name="gettype-operator-visual-basic"></a>Operatore GetType (Visual Basic)
Restituisce un <xref:System.Type> oggetto per il tipo specificato. Il <xref:System.Type> oggetto fornisce informazioni sul tipo, ad esempio le proprietà, metodi ed eventi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`typename`|Il nome del tipo per cui si desidera ottenere informazioni.|  
  
## <a name="remarks"></a>Note  
 Il `GetType` operatore restituisce il <xref:System.Type> oggetto per l'oggetto specificato `typename`. È possibile passare il nome di qualsiasi tipo definito in `typename`. Il comportamento predefinito include quanto segue:  
  
-   Tutti i dati di Visual Basic digitare, ad esempio `Boolean` o `Date`.  
  
-   Qualsiasi classe .NET Framework, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
-   Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.  
  
-   Qualsiasi matrice definita dall'applicazione.  
  
-   Qualsiasi delegato definito dall'applicazione.  
  
-   Qualsiasi enumerazione definito da Visual Basic, .NET Framework o l'applicazione.  
  
 Se si desidera ottenere l'oggetto di tipo di una variabile oggetto, usare il <xref:System.Type.GetType%2A?displayProperty=nameWithType> (metodo).  
  
 Il `GetType` operatore può essere utile nelle situazioni seguenti:  
  
-   È necessario accedere ai metadati per un tipo in fase di esecuzione. Il <xref:System.Type> oggetto fornisce metadati quali i membri dei tipi e le informazioni di distribuzione. È necessario, ad esempio, in modo da riflettere su un assembly. Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo. In caso affermativo, `GetType` restituisce i riferimenti allo stesso <xref:System.Type> oggetto.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano il `GetType` operatore in uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
