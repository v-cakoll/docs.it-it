---
title: "&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; è già implementata dalla classe di base &#39;&lt; nomeclassebase&gt;&#39;. Prevista nuova implementazione di &lt;tipo&gt; presuppone"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords: BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69884ed567e0046da5cf5c51b3e83e57e890d49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39; &lt;interfacename&gt;.&lt; MemberName&gt;&#39; è già implementata dalla classe di base &#39;&lt; nomeclassebase&gt;&#39;. Prevista nuova implementazione di &lt;tipo&gt; presuppone
Una proprietà, routine o evento in una classe derivata utilizza un `Implements` clausola che specifica un membro di interfaccia che è già implementato nella classe base.  
  
 Una classe derivata può reimplementare un membro di interfaccia implementato dalla sua classe base. Questo non equivale a eseguire l'override dell'implementazione della classe base. Per ulteriori informazioni, vedere [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42015  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se si intende reimplementare il membro di interfaccia, non occorre fare nulla. Codice nella classe derivata accede al membro reimplementato a meno che non si utilizza il `MyBase` (parola chiave) per accedere all'implementazione della classe di base.  
  
-   Se non si intende reimplementare il membro di interfaccia, rimuovere la clausola `Implements` dalla dichiarazione di proprietà, routine o evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
