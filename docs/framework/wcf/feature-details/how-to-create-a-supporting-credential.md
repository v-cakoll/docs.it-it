---
title: 'Procedura: creare una credenziale di supporto'
ms.date: 03/30/2017
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
ms.openlocfilehash: 3f33bf5a78c575237ee4bc609a482a81fd30fc53
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964554"
---
# <a name="how-to-create-a-supporting-credential"></a>Procedura: creare una credenziale di supporto
È possibile avere uno schema di sicurezza personalizzato che richiede più di una credenziale. Ad esempio, è possibile che un servizio richieda a un client non solo un nome utente e una password, ma anche una credenziale che dimostri che l'utente del client abbia un'età superiore a 18 anni. La seconda credenziale è una *credenziale di supporto*. In questo argomento viene illustrato come implementare tali credenziali in un client Windows Communication Foundation (WCF).  
  
> [!NOTE]
> La specifica per supportare le credenziali è parte della specifica SecurityPolicy-WS. Per ulteriori informazioni, vedere la pagina relativa alle [specifiche Web Services Security](https://docs.microsoft.com/previous-versions/dotnet/articles/ms951273(v=msdn.10)).  
  
## <a name="supporting-tokens"></a>Token di supporto  
 In breve, quando si utilizza la sicurezza dei messaggi, viene sempre utilizzata una *credenziale primaria* per proteggere il messaggio (ad esempio, un certificato X. 509 o un ticket Kerberos).  
  
 Come definito dalla specifica, un'associazione di sicurezza utilizza i *token* per proteggere lo scambio di messaggi. Un *token* è una rappresentazione di una credenziale di sicurezza.  
  
 L'associazione di sicurezza usa un token primario identificato nei criteri dell'associazione di sicurezza per creare una firma. Questa firma viene definita *firma del messaggio*.  
  
 È possibile specificare token aggiuntivi per aumentare le attestazioni fornite dal token associato alla firma del messaggio.  
  
## <a name="endorsing-signing-and-encrypting"></a>Verifica dell'autenticità, firma e crittografia  
 Una credenziale di supporto produce un *token di supporto* trasmesso all'interno del messaggio. La specifica WS-SecurityPolicy definisce quattro modalità per allegare un token di supporto al messaggio, come descritto nella tabella seguente.  
  
|Scopo|Descrizione|  
|-------------|-----------------|  
|Firmato|Il token di supporto viene incluso nell'intestazione di sicurezza e viene firmato con la firma del messaggio.|  
|Verifica dell'autenticità|Un *token di approvazione* firma la firma del messaggio.|  
|Firmato e di verifica dell'autenticità|I token di verifica dell'autenticità firmati firmano l'intero elemento `ds:Signature` prodotto dalla firma del messaggio e sono essi stessi firmati con la firma del messaggio; ovvero, entrambi i token, quello usato per la firma del messaggio e quello di verifica dell'autenticità firmato, si firmano l'un l'altro.|  
|Firmato e di crittografia|I token di supporto crittografati firmati sono token di supporto firmati che vengono anche crittografati quando sono presenti in `wsse:SecurityHeader`.|  
  
## <a name="programming-supporting-credentials"></a>Programmazione di credenziali di supporto  
 Per creare un servizio che usa token di supporto, è necessario creare un [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md). Per altre informazioni, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Quando si crea un'associazione personalizzata, il primo passaggio consiste nel creare un elemento di associazione di sicurezza che può essere di uno dei tre tipi seguenti:  
  
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Tutte le classi ereditano da <xref:System.ServiceModel.Channels.SecurityBindingElement>, che include quattro proprietà rilevanti:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a>Ambiti  
 Esistono due ambiti per le credenziali di supporto:  
  
- I *token di supporto dell'endpoint* supportano tutte le operazioni di un endpoint. In altre parole, la credenziale rappresentata dal token di supporto può essere usata ogni volta che vengono richiamate le operazioni di un endpoint.  
  
- I *token di supporto dell'operazione* supportano solo una specifica operazione dell'endpoint.  
  
 Come indicato dai nomi delle proprietà, le credenziali di supporto possono essere obbligatorie o facoltative. In altre parole, se la credenziale di supporto viene usata se presente, anche se non necessaria, l'autenticazione non avrà esito negativo se la credenziale non è presente.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a>Per creare un'associazione personalizzata che includa credenziali di supporto  
  
1. Creare un elemento di associazione di sicurezza. Nell'esempio seguente viene creata una classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con la modalità di autenticazione `UserNameForCertificate`. Usare il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.  
  
2. Aggiungere il parametro di supporto alla raccolta dei tipi restituita dalla proprietà appropriata (`Endorsing`, `Signed`, `SignedEncrypted` o `SignedEndorsed`). I tipi nello spazio dei nomi <xref:System.ServiceModel.Security.Tokens> includono tipi comunemente usati, ad esempio <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene creata un'istanza della classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e viene aggiunta un'istanza della classe <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> alla raccolta della proprietà Endorsing restituita.  
  
### <a name="code"></a>Codice  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
