---
title: "Procedura: Personalizzare un'associazione basata sul sistema"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: 0c5474a65bee7d3d290372e79f8423ea9986235f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301178"
---
# <a name="how-to-customize-a-system-provided-binding"></a>Procedura: Personalizzare un'associazione basata sul sistema
Windows Communication Foundation (WCF) include diverse associazioni fornite dal sistema che consentono di configurare alcune delle proprietà degli elementi di associazione sottostante, ma non tutte le proprietà. In questo argomento viene illustrato come impostare proprietà sugli elementi di associazione per creare un'associazione personalizzata.  
  
 Per altre informazioni su come creare e configurare gli elementi di associazione senza utilizzare le associazioni fornite dal sistema direttamente, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Per altre informazioni sulla creazione e l'estensione delle associazioni personalizzate, vedere [estensione delle associazioni](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
 In WCF tutte le associazioni sono costituite da *elementi di associazione*. Ogni elemento di associazione deriva dalla classe <xref:System.ServiceModel.Channels.BindingElement>. Le associazioni fornite dal sistema, ad esempio <xref:System.ServiceModel.BasicHttpBinding>, creano e configurano propri elementi di associazione. In questo argomento viene illustrato come accedere e modificare le proprietà di questi elementi di associazione che non sono direttamente esposte sull'associazione; in particolare, la classe <xref:System.ServiceModel.BasicHttpBinding>.  
  
 I singoli elementi di associazione contenuti in una raccolta rappresentata dal <xref:System.ServiceModel.Channels.BindingElementCollection> classe e vengono aggiunti nell'ordine indicato: Flusso delle transazioni, sessione affidabile, protezione, Duplex composito, unidirezionale, Stream Security, codifica dei messaggi e trasporto. Si noti che non tutti gli elementi di associazione elencati sono necessari in ogni associazione. In questa raccolta di elementi di associazione possono essere inclusi anche elementi di associazione definiti dall'utente, che devono essere visualizzati nello stesso ordine descritto in precedenza. Ad esempio, un trasporto definito dall'utente deve essere l'ultimo elemento della raccolta di elementi di associazione.  
  
 La classe <xref:System.ServiceModel.BasicHttpBinding> contiene tre elementi di associazione:  
  
1. Un elemento di associazione di sicurezza facoltativo: la classe <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> usata con il trasporto HTTP (protezione a livello di messaggio) o la classe <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> usata quando il livello di trasporto fornisce la protezione, caso in cui viene usato il trasporto HTTPS.  
  
2. Un elemento di associazione del codificatore dei messaggi obbligatorio: <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> o <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
3. Un elemento di associazione del trasporto obbligatorio: <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
 In questo esempio si crea un'istanza dell'associazione, generare una *binding personalizzato* da quest'ultimo, esaminare gli elementi di associazione nell'associazione personalizzata e quando si trova l'elemento di associazione HTTP, impostiamo relativo `KeepAliveEnabled` proprietà `false`. La proprietà `KeepAliveEnabled` non è esposta direttamente su `BasicHttpBinding`, pertanto è necessario creare un'associazione personalizzata per spostarsi verso il basso sull'elemento di associazione e impostare questa proprietà.  
  
### <a name="to-modify-a-system-provided-binding"></a>Per modificare un'associazione fornita dal sistema  
  
1. Creare un'istanza della classe <xref:System.ServiceModel.BasicHttpBinding> e impostarne la modalità di sicurezza a livello di messaggio.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2. Creare un'associazione personalizzata dall'associazione e creare una classe <xref:System.ServiceModel.Channels.BindingElementCollection> da una delle proprietà dell'associazione personalizzata.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3. Eseguire un ciclo nella classe <xref:System.ServiceModel.Channels.BindingElementCollection> e, quando viene trovata la classe <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, impostarne la proprietà <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> su `false`.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)
