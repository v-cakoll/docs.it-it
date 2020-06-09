---
title: "Procedura: creare un'associazione personalizzata usando SecurityBindingElement"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating custom bindings
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
ms.openlocfilehash: 15fdd50b05bd2217cb9819373cd1c015da52b15b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599009"
---
# <a name="how-to-create-a-custom-binding-using-the-securitybindingelement"></a>Procedura: creare un'associazione personalizzata usando SecurityBindingElement
Windows Communication Foundation (WCF) include diverse associazioni fornite dal sistema che possono essere configurate, ma non offrono la massima flessibilità durante la configurazione di tutte le opzioni di sicurezza supportate da WCF. In questo argomento viene illustrato come creare direttamente un'associazione personalizzata di singoli elementi di associazione e vengono evidenziate alcune impostazioni di sicurezza che è possibile specificare durante la creazione di tale associazione. Per ulteriori informazioni sulla creazione di associazioni personalizzate, vedere [estensione di binding](../extending/extending-bindings.md).  
  
> [!WARNING]
> <xref:System.ServiceModel.Channels.SecurityBindingElement> non supporta la forma di <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, vale a dire la forma di canale predefinita utilizzata dal trasporto TCP quando l'oggetto <xref:System.ServiceModel.TransferMode> è impostato su <xref:System.ServiceModel.TransferMode.Buffered>. È necessario impostare <xref:System.ServiceModel.TransferMode> su <xref:System.ServiceModel.TransferMode.Streamed> per utilizzare <xref:System.ServiceModel.Channels.SecurityBindingElement> in questo scenario.  
  
## <a name="creating-a-custom-binding"></a>Creazione di un'associazione personalizzata  
 In WCF tutte le associazioni sono costituite da *elementi di associazione*. Ogni elemento di associazione deriva dalla classe <xref:System.ServiceModel.Channels.BindingElement>. Per le associazioni standard fornite dal sistema, vengono creati e configurati gli elementi di associazione, sebbene sia possibile personalizzare alcune delle impostazioni delle proprietà.  
  
 Al contrario, per creare un'associazione personalizzata, vengono creati e configurati gli elementi di associazione dai quali viene creato <xref:System.ServiceModel.Channels.CustomBinding>.  
  
 A tale scopo, vengono aggiunti singoli elementi di associazione a una raccolta rappresentata da un'istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection>, quindi la proprietà `Elements` di `CustomBinding` viene impostata allo stesso modo dell'oggetto. È necessario aggiungere gli elementi di associazione nell'ordine seguente: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding e Transport. Si noti che non tutti gli elementi di associazione elencati sono necessari in ogni associazione.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 Tre elementi di associazione sono correlati alla protezione a livello di messaggio e sono tutti derivati dalla classe <xref:System.ServiceModel.Channels.SecurityBindingElement>. I tre elementi sono <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> viene utilizzato per fornire una protezione in modalità mista. Gli altri due elementi sono utilizzati quando la protezione è fornita dal livello di messaggio.  
  
 Le classi aggiuntive vengono utilizzate quando viene fornita la protezione a livello di trasporto:  
  
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Elementi di associazione obbligatori  
 Esiste un ampio numero di possibili elementi di associazione che si possono combinare in un'associazione. Non tutte queste combinazioni sono valide. Contenuto della sezione vengono descritti gli elementi obbligatori che devono essere presenti in un'associazione di sicurezza.  
  
 Le associazioni di sicurezza valide dipendono da molti fattori, tra cui:  
  
- Modalità di sicurezza.  
  
- Protocollo di trasporto.  
  
- Modello di scambio dei messaggi (MEP, Message Exchange Pattern) specificato nel contratto.  
  
 Nella tabella seguente vengono illustrate le configurazioni dello stack dell'elemento di associazione valide per ogni combinazione dei fattori precedenti. Si noti che si tratta di requisiti minimi. È possibile aggiungere ulteriori elementi all'associazione, ad esempio elementi di associazione di codifica dei messaggi, di transazione e di altro tipo.  
  
|Modalità di sicurezza|Trasporto|Modello di scambio dei messaggi del contratto|Modello di scambio dei messaggi del contratto|Modello di scambio dei messaggi del contratto|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|Trasporto|Https||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||SSL o Windows StreamSecurityBindingElement|SSL o Windows StreamSecurityBindingElement|SSL o Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Message|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (modalità di autenticazione = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||Tcp|SecurityBindingElement|SecurityBindingElement|SymmetricSecurityBindingElement (modalità di autenticazione = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Misto (trasporto con credenziali messaggio)|Https|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|SymmetricSecurityBindingElement (modalità di autenticazione = SecureConversation)|SymmetricSecurityBindingElement (modalità di autenticazione = SecureConversation)|  
|||OneWayBindingElement|||  
|||SSL o Windows StreamSecurityBindingElement|SSL o Windows StreamSecurityBindingElement|SSL o Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 Si noti che esistono molte impostazioni configurabili in SecurityBindingElements. Per altre informazioni, vedere [modalità di autenticazione di SecurityBindingElement](securitybindingelement-authentication-modes.md).  
  
 Per altre informazioni, vedere [conversazioni sicure e sessioni sicure](secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>Per creare un'associazione personalizzata che utilizza un SymmetricSecurityBindingElement  
  
1. Creare un'istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection> con il nome `outputBec`.  
  
2. Chiamare il metodo statico `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)` che restituisce un'istanza della classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3. Aggiungere <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> alla raccolta (`outputBec`) chiamando il metodo `Add` di <xref:System.Collections.ObjectModel.Collection%601> della classe <xref:System.ServiceModel.Channels.BindingElement>.  
  
4. Creare un'istanza della classe <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e aggiungerla alla raccolta (`outputBec`). In tal modo viene specificata la codifica utilizzata dall'associazione.  
  
5. Creare un <xref:System.ServiceModel.Channels.HttpTransportBindingElement> e aggiungerlo alla raccolta (`outputBec`). In tal modo viene specificato che l'associazione utilizza il trasporto HTTP.  
  
6. Creare una nuova associazione personalizzata creando un'istanza della classe <xref:System.ServiceModel.Channels.CustomBinding> e passando la raccolta `outputBec` al costruttore.  
  
7. L'associazione personalizzata risultante condivide molte delle stesse caratteristiche di <xref:System.ServiceModel.WSHttpBinding> standard. Specifica la protezione a livello di messaggio e le credenziali di Windows, ma disattiva le sessioni protette. Richiede che la credenziale del servizio venga specificata fuori banda e non crittografa le firme. È possibile controllare l'ultima solo impostando la proprietà <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> come indicato nel passaggio 4. Le altre possono essere controllate utilizzando le impostazioni nell'associazione standard.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente è riportata una funzione completa per creare un'associazione personalizzata che utilizza un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Codice  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Estensione delle associazioni](../extending/extending-bindings.md)
- [Associazioni fornite dal sistema](../system-provided-bindings.md)
