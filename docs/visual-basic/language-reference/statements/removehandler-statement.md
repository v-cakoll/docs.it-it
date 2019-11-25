---
title: Istruzione RemoveHandler
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333043"
---
# <a name="removehandler-statement"></a>Istruzione RemoveHandler
Removes the association between an event and an event handler.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`event`|The name of the event being handled.|  
|`eventhandler`|The name of the procedure currently handling the event.|  
  
## <a name="remarks"></a>Note  
 The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.  
  
> [!NOTE]
> For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor. For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
