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
ms.openlocfilehash: 43507ac8e9b5843e8fa9496737a3d77b3a425a7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963766"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Specifica che una proprietà può essere scritta ma non letta.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
 **Contesto di dichiarazione.** Si può usare `WriteOnly` solo a livello di modulo. Ciò significa che il contesto di Dichiarazione `WriteOnly` per una proprietà deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.  
  
 È possibile dichiarare una proprietà come `WriteOnly`, ma non come variabile.  
  
## <a name="when-to-use-writeonly"></a>Quando usare WriteOnly  
 In alcuni casi si vuole che il codice consumer sia in grado di impostare un valore, ma non di individuarne lo stato. Ad esempio, i dati sensibili, ad esempio un numero di registrazione sociale o una password, devono essere protetti dall'accesso da parte di qualsiasi componente che non lo ha impostato. In questi casi, è possibile usare una `WriteOnly` proprietà per impostare il valore.  
  
> [!IMPORTANT]
> Quando si definisce e si usa `WriteOnly` una proprietà, tenere presenti le misure di protezione aggiuntive seguenti:  
  
- **Override.** Se la proprietà è un membro di una classe, consentire l'impostazione predefinita di [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)e non dichiararla `Overridable` o `MustOverride`. In questo modo si impedisce a una classe derivata di effettuare l'accesso indesiderato tramite una sostituzione.  
  
- **Livello di accesso.** Se si mantengono i dati sensibili della proprietà in una o più variabili, dichiararli [privati](../../../visual-basic/language-reference/modifiers/private.md) in modo che nessun altro codice possa accedervi.  
  
- **Crittografia.** Archiviare tutti i dati sensibili in formato crittografato anziché in testo normale. Se il codice dannoso in qualche modo può accedere a tale area della memoria, è più difficile usare i dati. La crittografia è utile anche se è necessario serializzare i dati sensibili.  
  
- **Ripristino.** Quando la classe, la struttura o il modulo che definisce la proprietà viene terminato, reimpostare i dati sensibili sui valori predefiniti o su altri valori non significativi. Questo garantisce una protezione aggiuntiva quando l'area di memoria viene liberata per l'accesso generale.  
  
- **Persistenza.** Non rende permanente i dati sensibili, ad esempio su disco, se è possibile evitarli. Inoltre, non scrivere dati sensibili negli Appunti.  
  
 Il `WriteOnly` modificatore può essere usato in questo contesto:  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
