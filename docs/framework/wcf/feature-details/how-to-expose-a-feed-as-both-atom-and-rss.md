---
title: 'Procedura: esporre un feed come Atom e RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: e4ce1fa7b494c2317a1bddc57ee6b150c84b9a96
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593146"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a>Procedura: esporre un feed come Atom e RSS
Windows Communication Foundation (WCF) consente di creare un servizio che espone un feed di diffusione. In questo argomento viene illustrato come creare un servizio di diffusione che espone un feed di diffusione usando sia Atom 1.0 sia RSS 2.0. Questo servizio espone un endpoint che può restituire uno dei due formati di diffusione. Per motivi di semplicità, il servizio usato in questo esempio è indipendente. In un ambiente di produzione un servizio di questo tipo verrebbe ospitato da IIS o WAS. Per ulteriori informazioni sulle diverse opzioni di hosting WCF, vedere [hosting](hosting.md).  
  
### <a name="to-create-a-basic-syndication-service"></a>Per creare un servizio di diffusione di base  
  
1. Definire un contratto di servizio usando un'interfaccia contrassegnata con l'attributo <xref:System.ServiceModel.Web.WebGetAttribute>. Ogni operazione esposta come feed di diffusione restituisce un oggetto <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Si notino i parametri per <xref:System.ServiceModel.Web.WebGetAttribute>. `UriTemplate` specifica l'URL usato per richiamare questa operazione del servizio. La stringa per questo parametro contiene valori letterali e una variabile racchiusa tra parentesi graffe ({*Format*}). Questa variabile corrisponde al parametro `format` dell'operazione del servizio. Per altre informazioni, vedere <xref:System.UriTemplate>. `BodyStyle` incide sul modo in cui vengono scritti i messaggi inviati e ricevuti da e verso questa operazione del servizio. <xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> specifica che i dati inviati da e verso questa operazione del servizio non vengono incapsulati in elementi XML definiti dall'infrastruttura. Per altre informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle>.  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    > Usare <xref:System.ServiceModel.ServiceKnownTypeAttribute> per specificare i tipi restituiti dalle operazioni del servizio in questa interfaccia.  
  
2. Implementare il contratto di servizio  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3. Creare un oggetto <xref:System.ServiceModel.Syndication.SyndicationFeed> e aggiungere un autore, una categoria e una descrizione.  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4. Creare diversi oggetti <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5. Aggiungere gli oggetti <xref:System.ServiceModel.Syndication.SyndicationItem> al feed.  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6. Usare il parametro di formato per restituire il formato richiesto.  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>Per ospitare il servizio  
  
1. Creare un oggetto <xref:System.ServiceModel.Web.WebServiceHost>. La classe <xref:System.ServiceModel.Web.WebServiceHost> aggiunge automaticamente un endpoint nell'indirizzo di base del servizio, a meno che non ne sia specificato uno nel codice o nella configurazione. Poiché in questo esempio non è specificato alcun endpoint, viene esposto l'endpoint predefinito.  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2. Aprire l'host del servizio, caricare il feed dal servizio, visualizzare il feed e aspettare che l'utente prema INVIO.  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Per chiamare GetBlog con HTTP GET  
  
1. Aprire Internet Explorer, digitare l'URL seguente e premere INVIO: `http://localhost:8000/BlogService/GetBlog` .
  
     L'URL contiene l'indirizzo di base del servizio ( `http://localhost:8000/BlogService` ), l'indirizzo relativo dell'endpoint e l'operazione del servizio da chiamare.  
  
### <a name="to-call-getblog-from-code"></a>Per chiamare GetBlog() dal codice  
  
1. Creare un <xref:System.Xml.XmlReader> con l'indirizzo di base e il metodo che si sta chiamando.  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2. Chiamare il metodo statico <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> passando l'oggetto <xref:System.Xml.XmlReader> appena creato.  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     Verrà in tal modo richiamata l'operazione del servizio e verrà popolato un nuovo <xref:System.ServiceModel.Syndication.SyndicationFeed> con il formattatore restituito dall'operazione del servizio.  
  
3. Accedere all'oggetto feed.  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato il codice completo per questo esempio.  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Durante la compilazione del codice precedente, fare riferimento a System.ServiceModel.dll e a System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
