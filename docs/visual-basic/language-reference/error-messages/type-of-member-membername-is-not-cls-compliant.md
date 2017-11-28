---
title: "Tipo di membro &#39; &lt;membername&gt;&#39; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords: BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c09a71675275758220691ad09eeab48e53309f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a>Tipo di membro &#39; &lt;membername&gt;&#39; non è conforme a CLS
Il tipo di dati specificato per questo membro non è in parte il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) (CLS). Non si tratta di un errore all'interno del componente, poiché il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supporta questo tipo di dati. Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati. Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.  
  
 I tipi di dati di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] seguenti non sono compatibili con CLS:  
  
-   [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se il componente interagisce solo con altri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componenti o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.  
  
-   Se si prevede l'interazione con un componente non scritto per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], potrebbe essere in grado di determinare, tramite reflection o dalla documentazione, che supporta questo tipo di dati. In caso affermativo, non è necessario apportare alcuna modifica.  
  
-   Se si prevede l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
-   Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Ad esempio, `uint` è spesso a 16 bit in altri ambienti. Se si passa un argomento a 16 bit a tale componente, dichiararla come `UShort` anziché `UInteger` in gestito [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] codice.  
  
## <a name="see-also"></a>Vedere anche  
 [Reflection](../../../framework/reflection-and-codedom/reflection.md)  
 [\<PAVE su > scrittura di codice conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
