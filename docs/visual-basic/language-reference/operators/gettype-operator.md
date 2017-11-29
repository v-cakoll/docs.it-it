---
title: Operatore GetType (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a>Operatore GetType (Visual Basic)
Restituisce un <xref:System.Type> oggetto per il tipo specificato. Il <xref:System.Type> oggetto fornisce informazioni sul tipo, ad esempio la proprietà, metodi ed eventi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---|---|  
|`typename`|Il nome del tipo per cui si desidera ottenere informazioni.|  
  
## <a name="remarks"></a>Note  
 Il `GetType` operatore restituisce il <xref:System.Type> oggetto per l'oggetto specificato `typename`. È possibile passare il nome di qualsiasi tipo definito in `typename`. Il comportamento predefinito include quanto segue:  
  
-   Tipo di dati Visual Basic, ad esempio `Boolean` o `Date`.  
  
-   Qualsiasi classe .NET Framework, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
-   Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.  
  
-   Qualsiasi matrice definita dall'applicazione.  
  
-   Qualsiasi delegato definito dall'applicazione.  
  
-   Qualsiasi enumerazione definita da Visual Basic, .NET Framework o l'applicazione.  
  
 Se si desidera ottenere l'oggetto di tipo di una variabile oggetto, utilizzare il <xref:System.Type.GetType%2A?displayProperty=nameWithType> metodo.  
  
 Il `GetType` operatore può essere utile nei casi seguenti:  
  
-   È necessario accedere ai metadati per un tipo in fase di esecuzione. Il <xref:System.Type> oggetto fornisce metadati quali i membri dei tipi e le informazioni di distribuzione. È necessario, ad esempio, effettuare la reflection di un assembly. Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo. In caso affermativo, `GetType` restituisce riferimenti allo stesso <xref:System.Type> oggetto.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti viene illustrato il `GetType` operatore in uso.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
