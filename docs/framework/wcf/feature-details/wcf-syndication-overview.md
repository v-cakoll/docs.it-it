---
title: Panoramica sulla diffusione WCF
ms.date: 03/30/2017
ms.assetid: af6d4c39-e5e8-4099-aee6-5261feff9107
ms.openlocfilehash: c059ca3ee33b254a60d6b8596b02e1f995fd2ca1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498244"
---
# <a name="wcf-syndication-overview"></a>Panoramica sulla diffusione WCF
Windows Communication Foundation (WCF) fornisce supporto per l'esposizione di feed di diffusione da un servizio WCF. La diffusione è un meccanismo di integrazione delle applicazioni in cui un server espone alcuni dati dell'applicazione in un formato interoperativo noto come feed. Un feed è una raccolta di dati dell'applicazione costituito da alcuni metadati a livello feed (titolo, autore, URL e altri metadati) e da una serie di elementi feed. All'interno del feed, gli elementi feed sono di solito organizzati in ordine cronologico inverso. Un elemento feed è costituito da un set standard di metadati di livello feed (titolo, URL, data di creazione, categoria e altri metadati di livello elemento) e da una quantità arbitraria di dati specifici dell'applicazione. I due tipi più comuni di feed di diffusione sono RSS Really Simple Syndication () 2.0 e Atom 1.0, entrambi i quali sono supportati da WCF.  
  
## <a name="object-model"></a>Modello a oggetti  
 WCF definisce un set di classi specifiche della diffusione che consentono di utilizzare feed, elementi feed e metadati correlati in modo indipendente dal formato: <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationPerson>, <xref:System.ServiceModel.Syndication.SyndicationLink>e altre classi specifiche della diffusione. WCF definisce inoltre le classi di infrastruttura che basare il modello di programmazione WCF REST per fornire inclusi supporto diffusione: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>, e <!--zz <xref:System.ServiceModel.Syndication.RSS20FeedFormatter>--> `RSS20FeedFormatter`. Le classi formatter di feed supportano la serializzazione del modello a oggetti da e verso RSS 2.0 e Atom 1.0.  
  
## <a name="scenarios"></a>Scenari  
 Un utilizzo comune della diffusione è oggi rappresentato dal blogging, processo con cui l'autore di un blog pubblica periodicamente alcuni tipi di informazioni, tra cui testo, immagini o audio. Anche molti giornali e riviste pubblicano nuove storie o articoli utilizzando la diffusione. Eseguendo la sottoscrizione a un feed di questo genere, un utente può ricevere tutte le nuove informazioni provenienti da tali siti. Anche se la diffusione è più frequentemente associata a blog ed editori, può essere utilizzata con qualsiasi applicazione che esponga una raccolta di informazioni; ad esempio, un database dei bug che si desidera esporre utilizzando un feed di diffusione. È possibile creare un servizio WCF che espone un'operazione denominata `CodeDefects`. Questa operazione può accettare un parametro che specifica l'indirizzo di posta elettronica della persona di cui si desidera recuperare i bug. Un client può utilizzare l'URL seguente per chiamare l'operazione: http://someserver/bugDatabase/CodeDefects?user=johndoe.  
  
## <a name="syndication-formats"></a>Formati di diffusione  
 La piattaforma di diffusione WCF supporta RSS 2.0 e Atom 1.0.  
  
## <a name="see-also"></a>Vedere anche  
 [Modello di programmazione HTTP Web di WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
