---
title: Serializzazione SOAP e XML
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: dcb2ed1703473be582a12f430d2e051d8a420230
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588380"
---
# <a name="xml-and-soap-serialization"></a>Serializzazione SOAP e XML

La serializzazione XML converte (serializza) i campi pubblici e le proprietà di un oggetto, nonché i parametri e i valori restituiti dei metodi, in un flusso XML conforme a un documento XSD (XML Schema Definition Language) specifico. La serializzazione XML produce classi fortemente tipizzate con campi e proprietà pubbliche convertiti in un formato seriale (in questo caso XML) per l'archiviazione o il trasporto.

Dal momento che XML è uno standard aperto, il flusso XML può essere elaborato da qualsiasi applicazione, in base alle necessità, indipendentemente dalla piattaforma. Ad esempio, i servizi Web XML creati tramite ASP.NET, utilizzano la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML che passano dati tra applicazioni del servizio Web XML tramite Internet o sulle Intranet. Al contrario, la deserializzazione prende tale flusso XML e ricostruisce l'oggetto.

La serializzazione XML può essere utilizzata anche per serializzare oggetti nei flussi XML conformi alla specifica SOAP. Il SOAP è un protocollo basato su XML, specificamente progettato per trasportare chiamate di routine mediante XML.

Per serializzare o deserializzare oggetti, utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>. Per creare le classi da serializzare, utilizzare lo strumento XML Schema Definition.

## <a name="see-also"></a>Vedi anche

- [Serializzazione binaria](binary-serialization.md)
- [Servizi Web XML creati con ASP.NET e client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
