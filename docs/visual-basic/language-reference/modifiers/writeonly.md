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
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599203"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Specifica che è possibile scritta una proprietà ma non è stato letto.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
 **Contesto della dichiarazione.** Si può usare `WriteOnly` solo a livello di modulo. Ciò significa che il contesto della dichiarazione per un `WriteOnly` proprietà deve essere una classe, struttura o modulo e non può essere un file di origine, lo spazio dei nomi o stored procedure.  
  
 È possibile dichiarare una proprietà come `WriteOnly`, ma non una variabile.  
  
## <a name="when-to-use-writeonly"></a>Quando utilizzare WriteOnly  
 Talvolta il codice in grado di impostare un valore senza scoprire che cos'è utilizzato. Ad esempio, i dati sensibili, ad esempio un codice fiscale o una password, debbano essere protetti dall'accesso da qualsiasi componente che non è stata impostata. In questi casi, è possibile utilizzare un `WriteOnly` proprietà per impostare il valore.  
  
> [!IMPORTANT]
>  Quando si definisce e utilizzare un `WriteOnly` proprietà, considerare le misure di protezione aggiuntive seguenti:  
  
-   **Si esegue l'override.** Se la proprietà è un membro di una classe, per impostazione predefinita per consentire [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)e non dichiararla `Overridable` o `MustOverride`. Ciò impedisce che una classe derivata effettua l'accesso indesiderato tramite una sostituzione.  
  
-   **Livello di accesso.** Se sono contenuti dati sensibili della proprietà in una o più variabili, dichiarare [privata](../../../visual-basic/language-reference/modifiers/private.md) in modo che nessun altro codice possa accedervi.  
  
-   **Crittografia.** Archiviare tutti i dati sensibili in forma crittografata anziché in testo normale. Se il codice dannoso in qualche modo accede a tale area di memoria, è difficile utilizzare i dati. La crittografia è utile anche se è necessario serializzare i dati sensibili.  
  
-   **La reimpostazione.** Quando la classe, struttura o modulo che definisce la proprietà viene terminato, reimpostare i dati sensibili sui valori predefiniti o ad altri valori non significativi. Ciò fornisce una protezione aggiuntiva quando tale area di memoria viene liberata per l'accesso generale.  
  
-   **Persistenza.** Tutti i dati riservati, ad esempio su disco, non vengono mantenute se non è possibile evitare. Inoltre, non scrivere i dati sensibili negli Appunti.  
  
 Il `WriteOnly` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
