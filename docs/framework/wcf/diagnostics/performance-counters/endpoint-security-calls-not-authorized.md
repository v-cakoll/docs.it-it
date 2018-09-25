---
title: 'Endpoint: chiamate di sicurezza non autorizzate'
ms.date: 03/30/2017
ms.assetid: d25095ff-9ff0-4c69-a674-4e6a9fe3f4dc
author: BrucePerlerMS
ms.openlocfilehash: 2d2f114d45675ece23f818d4d56bcc40684f9dbf
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47156292"
---
# <a name="endpoint-security-calls-not-authorized"></a>Endpoint: chiamate di sicurezza non autorizzate
Nome contatore: chiamate di sicurezza non autorizzate.  
  
## <a name="description"></a>Descrizione  
 Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`. Indica che il messaggio in ingresso proviene da un utente valido ed è adeguatamente protetto, ma l'utente non è autorizzato a eseguire attività specifiche.
