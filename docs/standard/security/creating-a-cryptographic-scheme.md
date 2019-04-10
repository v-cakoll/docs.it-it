---
title: Creazione di uno schema di crittografia
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ef3741ef5cec720c2fb285c9aa60d610acc0be9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321653"
---
# <a name="creating-a-cryptographic-scheme"></a>Creazione di uno schema di crittografia
I componenti di crittografia di .NET Framework possono essere combinati per creare diversi schemi per la crittografia e la decrittografia dei dati.  
  
 Uno schema di crittografia semplice per la crittografia e la decrittografia dei dati può specificare i passaggi seguenti:  
  
1. Ogni parte genera una coppia di chiavi pubblica/privata.  
  
2. Le parti si scambiano le chiavi pubbliche.  
  
3. Ogni parte genera una chiave segreta per la crittografia TripleDES, ad esempio, e crittografa la nuova chiave creata usando la chiave pubblica dell'altra parte.  
  
4. Ogni parte invia i dati all'altra parte e combina la chiave segreta dell'altra parte con la propria, in un ordine specifico, per creare una nuova chiave segreta.  
  
5. Le parti avviano quindi una conversazione usando la crittografia simmetrica.  
  
 La creazione di uno schema di crittografia non è un'attività banale.
  
## <a name="see-also"></a>Vedere anche

- [servizi crittografici](../../../docs/standard/security/cryptographic-services.md)
