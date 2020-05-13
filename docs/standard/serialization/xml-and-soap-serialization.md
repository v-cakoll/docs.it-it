---
title: Serializzazione SOAP e XML
description: In questa panoramica viene illustrata la serializzazione XML, che può essere utilizzata per serializzare oggetti in flussi XML conformi alla specifica SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: 6b7d6f59694a28207758fa7772781eed073917e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379536"
---
# <a name="xml-and-soap-serialization"></a>Serializzazione SOAP e XML

La serializzazione XML converte (serializza) i campi pubblici e le proprietà di un oggetto, nonché i parametri e i valori restituiti dei metodi, in un flusso XML conforme a un documento XSD (XML Schema Definition Language) specifico. La serializzazione XML produce classi fortemente tipizzate con campi e proprietà pubbliche convertiti in un formato seriale (in questo caso XML) per l'archiviazione o il trasporto.

Dal momento che XML è uno standard aperto, il flusso XML può essere elaborato da qualsiasi applicazione, in base alle necessità, indipendentemente dalla piattaforma. Ad esempio, i servizi Web XML creati tramite ASP.NET, utilizzano la classe <xref:System.Xml.Serialization.XmlSerializer> per creare flussi XML che passano dati tra applicazioni del servizio Web XML tramite Internet o sulle Intranet. Al contrario, la deserializzazione prende tale flusso XML e ricostruisce l'oggetto.

La serializzazione XML può essere utilizzata anche per serializzare oggetti nei flussi XML conformi alla specifica SOAP. Il SOAP è un protocollo basato su XML, specificamente progettato per trasportare chiamate di routine mediante XML.

Per serializzare o deserializzare oggetti, utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>. Per creare le classi da serializzare, utilizzare lo strumento XML Schema Definition.

## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- [Servizi Web XML creati con ASP.NET e client di servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
