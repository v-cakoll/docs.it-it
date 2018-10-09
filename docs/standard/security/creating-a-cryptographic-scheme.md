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
ms.openlocfilehash: 51d07fadcf359c2b44f22ca9868d0f12e24b80c5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873119"
---
# <a name="creating-a-cryptographic-scheme"></a>Creazione di uno schema di crittografia
I componenti di crittografia di .NET Framework possono essere combinati per creare diversi schemi per la crittografia e la decrittografia dei dati.  
  
 Uno schema di crittografia semplice per la crittografia e la decrittografia dei dati può specificare i passaggi seguenti:  
  
1.  Ogni parte genera una coppia di chiavi pubblica/privata.  
  
2.  Le parti si scambiano le chiavi pubbliche.  
  
3.  Ogni parte genera una chiave segreta per la crittografia TripleDES, ad esempio, e crittografa la nuova chiave creata usando la chiave pubblica dell'altra parte.  
  
4.  Ogni parte invia i dati all'altra parte e combina la chiave segreta dell'altra parte con la propria, in un ordine specifico, per creare una nuova chiave segreta.  
  
5.  Le parti avviano quindi una conversazione usando la crittografia simmetrica.  
  
 La creazione di uno schema di crittografia non è un'attività banale.
  
## <a name="see-also"></a>Vedere anche

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
