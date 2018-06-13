---
title: Attributi per il controllo della serializzazione SOAP codificata
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: b7f0d8bf7c7c1013937f7ce0a87c326b707fbc6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582422"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Attributi per il controllo della serializzazione SOAP codificata 
Il documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium (www.w3.org) contiene una sezione facoltativa (la sezione 5) che descrive le modalità di codifica dei parametri SOAP. Per ottenere la conformità alla sezione 5 delle specifiche, è necessario usare un set speciale di attributi reperibile nello spazio dei nomi <xref:System.Xml.Serialization>. Applicare tali attributi nel modo appropriato alle classi e ai membri delle classi, quindi utilizzare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le istanze della classe o delle classi.  
  
 Nella seguente tabella sono illustrati gli attributi, dove è possibile applicarli e la loro funzione. Per altre informazioni sull'utilizzo di questi attributi per il controllo della serializzazione XML, vedere [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) e [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md).  
  
 Per altre informazioni sugli attributi, vedere [Attributi](../../../docs/standard/attributes/index.md).  
  
|Attributo|Si applica a|Specifica|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|Campo pubblico, proprietà, parametro o valore restituito.|Il membro della classe sarà serializzato come attributo XML.|  
|<xref:System.Xml.Serialization.SoapElementAttribute>|Campo pubblico, proprietà, parametro o valore restituito.|La classe verrà serializzata come elemento XML.|  
|<xref:System.Xml.Serialization.SoapEnumAttribute>|Campo pubblico che rappresenta un identificatore dell'enumerazione.|Il nome dell'elemento di un membro dell'enumerazione.|  
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|Proprietà e campi pubblici|La proprietà o il campo devono essere ignorati se la classe che li contiene è serializzata.|  
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|Dichiarazioni della classe derivata pubblica e metodi pubblici per i documenti del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language).|Il tipo deve essere incluso durante la generazione degli schemi (per essere riconosciuto se serializzato).|  
|<xref:System.Xml.Serialization.SoapTypeAttribute>|Dichiarazioni di classe pubblica|La classe deve essere serializzata come un tipo XML.|  
  
## <a name="see-also"></a>Vedere anche  
 [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 [Attributi](../../../docs/standard/attributes/index.md)  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
