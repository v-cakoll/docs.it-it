---
title: '&#39;&lt;ElementName&gt; &#39; è obsoleto (avviso di Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: eeeca3354592bfc6d657b435c42ad5644fd2b97d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552390"
---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a>&#39;&lt;ElementName&gt; &#39; è obsoleto (avviso di Visual Basic)
Un'istruzione prova ad accedere a un elemento di programmazione che è stato contrassegnato con l'attributo <xref:System.ObsoleteAttribute> e la direttiva di considerarlo come un avviso.  
  
 È possibile contrassegnare qualsiasi elemento di programmazione come non più in uso applicando <xref:System.ObsoleteAttribute> a tale elemento. In questo caso, è possibile impostare la proprietà <xref:System.ObsoleteAttribute.IsError%2A> dell'attributo su `True` o `False`. Se si imposta la proprietà su `True`, il compilatore considera il tentativo di usare l'elemento come un errore. Se si imposta la proprietà su `False`, o si lascia l'impostazione predefinita `False`, il compilatore genera un avviso se si prova a usare l'elemento.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso perché la proprietà <xref:System.ObsoleteAttribute.IsError%2A> di <xref:System.ObsoleteAttribute> è `False`. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40008  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Verificare che nel riferimento del codice sorgente il nome dell'elemento sia stato digitato correttamente.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
