---
title: WriteOnly
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
ms.openlocfilehash: a9fa0a3a23561215d6ff122bc8e609b68ca6fc30
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386634"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Specifica che una proprietà può essere scritta ma non letta.  
  
## <a name="remarks"></a>Commenti  
  
## <a name="rules"></a>Regole  
 **Contesto della dichiarazione. ** Si può usare `WriteOnly` solo a livello di modulo. Ciò significa che il contesto di dichiarazione per una `WriteOnly` proprietà deve essere una classe, una struttura o un modulo e non può essere un file di origine, uno spazio dei nomi o una procedura.  
  
 È possibile dichiarare una proprietà come `WriteOnly` , ma non come variabile.  
  
## <a name="when-to-use-writeonly"></a>Quando usare WriteOnly  
 In alcuni casi si vuole che il codice consumer sia in grado di impostare un valore, ma non di individuarne lo stato. Ad esempio, i dati sensibili, ad esempio un numero di registrazione sociale o una password, devono essere protetti dall'accesso da parte di qualsiasi componente che non lo ha impostato. In questi casi, è possibile usare una `WriteOnly` proprietà per impostare il valore.  
  
> [!IMPORTANT]
> Quando si definisce e si usa una `WriteOnly` proprietà, tenere presenti le misure di protezione aggiuntive seguenti:  
  
- **Override.** Se la proprietà è un membro di una classe, consentire l'impostazione predefinita di [NotOverridable](notoverridable.md)e non dichiararla `Overridable` o `MustOverride` . In questo modo si impedisce a una classe derivata di effettuare l'accesso indesiderato tramite una sostituzione.  
  
- **Livello di accesso.** Se si mantengono i dati sensibili della proprietà in una o più variabili, dichiararli [privati](private.md) in modo che nessun altro codice possa accedervi.  
  
- **Crittografia.** Archiviare tutti i dati sensibili in formato crittografato anziché in testo normale. Se il codice dannoso in qualche modo può accedere a tale area della memoria, è più difficile usare i dati. La crittografia è utile anche se è necessario serializzare i dati sensibili.  
  
- **Ripristino.** Quando la classe, la struttura o il modulo che definisce la proprietà viene terminato, reimpostare i dati sensibili sui valori predefiniti o su altri valori non significativi. Questo garantisce una protezione aggiuntiva quando l'area di memoria viene liberata per l'accesso generale.  
  
- **Persistenza.** Non rende permanente i dati sensibili, ad esempio su disco, se è possibile evitarli. Inoltre, non scrivere dati sensibili negli Appunti.  
  
 Il `WriteOnly` modificatore può essere usato in questo contesto:  
  
 [Property Statement](../statements/property-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [ReadOnly](readonly.md)
- [Privata](private.md)
- [Parole chiave](../keywords/index.md)
