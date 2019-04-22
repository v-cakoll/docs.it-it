---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 1b8de27e872914ba59d73126d2a9a7c42609165e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829026"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Specifica che è possibile scritta una proprietà ma non letto.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
 **Contesto della dichiarazione.** Si può usare `WriteOnly` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `WriteOnly` proprietà deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o procedure.  
  
 È possibile dichiarare una proprietà come `WriteOnly`, ma non una variabile.  
  
## <a name="when-to-use-writeonly"></a>Quando usare WriteOnly  
 A volte si desidera che il codice dispendiosa in termini di essere in grado di impostare un valore, ma non scoprire che cos'è. Ad esempio, i dati sensibili, ad esempio un codice fiscale o una password, devono essere protetti dall'accesso da qualsiasi componente che non è stata impostata. In questi casi, è possibile usare un `WriteOnly` proprietà per impostare il valore.  
  
> [!IMPORTANT]
>  Quando si definiscono e utilizzano un `WriteOnly` proprietà, prendere in considerazione le misure di protezione aggiuntive seguenti:  
  
-   **Overriding.** Se la proprietà è un membro di una classe, per impostazione predefinita per consentire [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)e non viene dichiarato `Overridable` o `MustOverride`. Ciò impedisce che una classe derivata effettua l'accesso non desiderato tramite una sostituzione.  
  
-   **Livello di accesso.** Se sono contenuti dati sensibili della proprietà in una o più variabili, dichiararli [privato](../../../visual-basic/language-reference/modifiers/private.md) in modo che nessun altro codice possa accedervi.  
  
-   **Crittografia.** Store tutti i dati sensibili in forma crittografata piuttosto che in testo normale. Se codice dannoso in qualche modo accede a tale area di memoria, è più difficile apportare uso dei dati. La crittografia è utile anche se è necessario serializzare i dati sensibili.  
  
-   **Resetting.** Quando viene terminato la classe, struttura o modulo che definisce la proprietà, ripristinare i dati sensibili ai valori predefiniti o ad altri valori non significativi. Ciò offre protezione aggiuntiva quando tale area di memoria viene liberata per l'accesso generale.  
  
-   **Persistenza.** Non vengono mantenute eventuali dati sensibili, ad esempio su disco, se è possibile evitarlo. Inoltre, non scrivere tutti i dati riservati negli Appunti.  
  
 Il `WriteOnly` modificatore può essere usato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
