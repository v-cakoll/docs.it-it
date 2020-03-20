---
title: "Procedura: creare un'attestazione personalizzata"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: e78f577e0fd3473575fab998e55616936212ebb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185611"
---
# <a name="how-to-create-a-custom-claim"></a>Procedura: creare un'attestazione personalizzata
L'infrastruttura del modello di identità in Windows Communication Foundation (WCF) fornisce un <xref:System.IdentityModel.Claims.Claim> set di diritti e tipi di attestazione incorporati con le funzioni di supporto per la creazione di istanze con tali tipi e diritti. Queste attestazioni predefinite sono progettate per modellare le informazioni presenti nei tipi di credenziali client supportati da WCF per impostazione predefinita. In molti casi, le attestazioni incorporate sono sufficienti; tuttavia alcune applicazioni possono richiedere attestazioni personalizzate. Un'attestazione è costituita dal tipo di attestazione, dalla risorsa a cui si applica l'attestazione e dal diritto asserito sulla risorsa in questione. In questo argomento viene descritto come creare un'attestazione personalizzata.  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a>Per creare un'attestazione personalizzata basata su un tipo di dati primitivo  
  
1. Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.  
  
    1. Stabilire un valore univoco per il tipo di attestazione.  
  
         Il tipo di attestazione è un identificatore di stringa univoco. È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco. Per un elenco dei tipi di attestazione <xref:System.IdentityModel.Claims.ClaimTypes> definiti da WCF, vedere la classe .  
  
    2. Scegliere il tipo di dati primitivo e il valore della risorsa.  
  
         Una risorsa è un oggetto. Il tipo CLR della risorsa può essere primitivo, ad esempio <xref:System.String> o <xref:System.Int32> o qualsiasi tipo serializzabile. Il tipo CLR della risorsa deve essere serializzabile, perché le attestazioni vengono serializzate in vari punti da WCF. I tipi primitivi sono serializzabili.  
  
    3. Scegliere un diritto definito da WCF o un valore univoco per un diritto personalizzato.  
  
         Un diritto è un identificatore di stringa univoco. I diritti definiti da WCF sono <xref:System.IdentityModel.Claims.Rights> definiti nella classe .  
  
         È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.  
  
         Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/simplecustomclaim`, per una risorsa denominata `Driver's License`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a>Per creare un'attestazione personalizzata basata su un tipo di dati non primitivo  
  
1. Creare un'attestazione personalizzata passando il tipo di attestazione, il valore della risorsa e il diritto al costruttore <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.  
  
    1. Stabilire un valore univoco per il tipo di attestazione.  
  
         Il tipo di attestazione è un identificatore di stringa univoco. È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il tipo di attestazione sia univoco. Per un elenco dei tipi di attestazione <xref:System.IdentityModel.Claims.ClaimTypes> definiti da WCF, vedere la classe .  
  
    2. Scegliere o definire un tipo non primitivo serializzabile per la risorsa.  
  
         Una risorsa è un oggetto. Il tipo CLR della risorsa deve essere serializzabile, perché le attestazioni vengono serializzate in vari punti da WCF. I tipi primitivi sono già serializzabili.  
  
         Quando viene definito un nuovo tipo, applicare <xref:System.Runtime.Serialization.DataContractAttribute> alla classe. Applicare inoltre l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a tutti i membri del nuovo tipo che devono essere serializzati come parte dell'attestazione.  
  
         Nell'esempio di codice seguente viene definito un tipo di risorsa personalizzato denominato `MyResourceType`.  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. Scegliere un diritto definito da WCF o un valore univoco per un diritto personalizzato.  
  
         Un diritto è un identificatore di stringa univoco. I diritti definiti da WCF sono <xref:System.IdentityModel.Claims.Rights> definiti nella classe .  
  
         È responsabilità di chi progetta l'attestazione personalizzata assicurare che l'identificatore di stringa usato per il diritto sia univoco.  
  
         Nell'esempio di codice seguente viene creata un'attestazione personalizzata con un tipo di attestazione `http://example.org/claims/complexcustomclaim`, per un tipo di risorse personalizzato `MyResourceType`, e con il diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come creare un'attestazione personalizzata con un tipo di risorsa primitivo e un'attestazione personalizzata con un tipo di risorsa non primitivo.  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Gestione di attestazioni e autorizzazioni con il modello di identità](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
