---
title: Ricerca di attestazioni in un ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 81212d5b85ec516ae69c9c015c147cd011a9fd14
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495120"
---
# <a name="finding-claims-in-a-claimset"></a>Ricerca di attestazioni in un ClaimSet
L'esame del contenuto di una classe <xref:System.IdentityModel.Claims.ClaimSet> per particolari tipi di attestazioni è un'attività comune quando si utilizza l'autorizzazione basata sulle attestazioni. Per esaminare una classe <xref:System.IdentityModel.Claims.ClaimSet> al fine di verificare la presenza di attestazioni particolari, utilizzare il metodo <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>. Questo metodo fornisce prestazioni migliori che non l'iterazione diretta su <xref:System.IdentityModel.Claims.ClaimSet>. Nell'esempio seguente viene illustrata questa sintassi. Si noti che i parametri `claimType` e `claimRight` possono essere `null`. In tal caso i parametri corrisponderanno a tutti i tipi e i diritti di attestazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- [Gestione delle attestazioni e dell'autorizzazione con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
