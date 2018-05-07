---
title: 'Procedura: riferimenti coerenti ai certificati X.509'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: efc4fb399224de7f03c6bffb606178184de1d467
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Procedura: riferimenti coerenti ai certificati X.509
È possibile identificare un certificato in diversi modi: in base all'hash del certificato, l'identificatore SKI e l'autorità emittente con il numero di serie. L'identificatore SKI offre un sistema di identificazione univoca per la chiave pubblica del soggetto del certificato e viene spesso utilizzato con le firme digitali XML. Il valore SKI generalmente fa parte del certificato x. 509 come un *estensione del certificato x. 509*. Windows Communication Foundation (WCF) è un valore predefinito *stile di riferimento* che utilizza l'autorità emittente e il numero di serie se l'estensione SKI manca il certificato. Se il certificato contiene l'estensione SKI, lo stile di riferimento predefinito utilizza l'identificatore SKI per puntare al certificato. Se strada durante lo sviluppo di un'applicazione, si passa dall'utilizzo di certificati che non utilizzano l'estensione SKI a certificati che utilizzano l'estensione SKI, cambia anche lo stile di riferimento utilizzato nei messaggi generati WCF.  
  
 Se è necessario un stile di riferimento coerente indipendentemente dalla presenza dell'estensione SKI, è possibile configurare lo stile desiderato come illustrato nel codice seguente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un elemento di associazione di sicurezza personalizzato che utilizza un unico stile di riferimento coerente, il nome dell'autorità emittente e il numero di serie.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice sono necessari gli spazi dei nomi seguenti:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
