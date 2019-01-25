---
title: Impossibile fare riferimento a &#39; &lt;name&gt; &#39; perché è un membro del campo valori &#39; &lt;name&gt; &#39; della classe &#39; &lt;classname&gt; &#39;con &#39;System. MarshalByRefObject&#39; come classe di base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739297"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Impossibile fare riferimento a &#39; &lt;name&gt; &#39; perché è un membro del campo valori &#39; &lt;name&gt; &#39; della classe &#39; &lt;classname&gt; &#39;con &#39;System. MarshalByRefObject&#39; come classe di base
Il `System.MarshalByRefObject` classe consente alle applicazioni che supportano l'accesso remoto a oggetti attraverso limiti di dominio. I tipi devono ereditare dal `MarshalByRejectObject` classe quando viene utilizzato il tipo superando i limiti di dominio di applicazione. Lo stato dell'oggetto non deve essere copiato perché i membri dell'oggetto non sono utilizzabili all'esterno del dominio applicazione in cui sono stati creati.  
  
 **ID errore:** BC30310  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare il riferimento per assicurarsi che il membro a cui si fa riferimento è valido.  
  
2.  Qualificare in modo esplicito il membro con il `Me` (parola chiave).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.MarshalByRefObject>
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
