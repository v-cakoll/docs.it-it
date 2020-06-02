---
title: Attributi per il controllo della serializzazione XML
description: Questo articolo contiene gli attributi che è possibile applicare alle classi e ai membri delle classi per controllare il modo in cui XmlSerializer serializza o deserializza un'istanza di una classe.
ms.date: 03/30/2017
helpviewer_keywords:
- classes, serializing
- XmlSerializer class, serializing
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
- XML Schema, serializing
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
ms.openlocfilehash: fbc42ff696107f4a1b06d3611fc97a09cc4a3542
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276699"
---
# <a name="attributes-that-control-xml-serialization"></a>Attributi per il controllo della serializzazione XML
È possibile applicare gli attributi riportati nella seguente tabella alle classi e ai membri delle classi per controllare le modalità di serializzazione o deserializzazione di un'istanza della classe da parte di <xref:System.Xml.Serialization.XmlSerializer>. Per comprendere in che modo gli attributi controllano la serializzazione XML, vedere [Controllo della serializzazione XML mediante attributi](controlling-xml-serialization-using-attributes.md).  
  
 Tali  attributi possono inoltre essere utilizzati per controllare i messaggi SOAP in stile letterale generati da qualsiasi servizio Web XML. Per altre informazioni sull'applicazione di questi attributi a un metodo dei servizi Web XML, vedere [Serializzazione XML mediante servizi Web XML](xml-serialization-with-xml-web-services.md).  
  
 Per altre informazioni sugli attributi, vedere [Attributi](../attributes/index.md).  
  
|Attributo|Si applica a|Specifica|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.XmlAnyAttributeAttribute>|Campo pubblico, proprietà, parametro o valore restituito che restituiscono una matrice di oggetti <xref:System.Xml.XmlAttribute>.|Durante la deserializzazione, la matrice verrà riempita con oggetti <xref:System.Xml.XmlAttribute> che rappresentano tutti gli attributi XML ignoti allo schema.|  
|<xref:System.Xml.Serialization.XmlAnyElementAttribute>|Campo pubblico, proprietà, parametro o valore restituito che restituiscono una matrice di oggetti <xref:System.Xml.XmlElement>.|Durante la deserializzazione, la matrice viene riempita con oggetti <xref:System.Xml.XmlElement> che rappresentano tutti gli elementi XML ignoti allo schema.|  
|<xref:System.Xml.Serialization.XmlArrayAttribute>|Campo pubblico, proprietà, parametro o valore restituito che restituiscono una matrice di oggetti complessi.|I membri della matrice verranno generati come membri di una matrice XML.|  
|<xref:System.Xml.Serialization.XmlArrayItemAttribute>|Campo pubblico, proprietà, parametro o valore restituito che restituiscono una matrice di oggetti complessi.|I tipi derivati che possono essere inseriti in una matrice. Applicati di solito congiuntamente a un <xref:System.Xml.Serialization.XmlArrayAttribute>.|  
|<xref:System.Xml.Serialization.XmlAttributeAttribute>|Campo pubblico, proprietà, parametro o valore restituito.|Il membro sarà serializzato come attributo XML.|  
|<xref:System.Xml.Serialization.XmlChoiceIdentifierAttribute>|Campo pubblico, proprietà, parametro o valore restituito.|È possibile risolvere ulteriormente l'ambiguità del membro tramite l'utilizzo di un'enumerazione.|  
|<xref:System.Xml.Serialization.XmlElementAttribute>|Campo pubblico, proprietà, parametro o valore restituito.|Il campo o la proprietà verranno serializzati come elemento XML.|  
|<xref:System.Xml.Serialization.XmlEnumAttribute>|Campo pubblico che rappresenta un identificatore dell'enumerazione.|Il nome dell'elemento di un membro dell'enumerazione.|  
|<xref:System.Xml.Serialization.XmlIgnoreAttribute>|Proprietà e campi pubblici|La proprietà o il campo devono essere ignorati se la classe che li contiene è serializzata.|  
|<xref:System.Xml.Serialization.XmlIncludeAttribute>|Dichiarazioni della classe derivata pubblica e valori restituiti di metodi pubblici per i documenti del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language).|La classe deve essere inclusa durante la generazione degli schemi (per essere riconosciuta se serializzata).|  
|<xref:System.Xml.Serialization.XmlRootAttribute>|Dichiarazioni di classe pubblica|Controlla la serializzazione XML della destinazione dell'attributo come un elemento radice XML. Utilizzare l'attributo per specificare ulteriormente lo spazio dei nomi e il nome dell'elemento.|  
|<xref:System.Xml.Serialization.XmlTextAttribute>|Proprietà e campi pubblici|La proprietà o il campo devono essere serializzati come testo XML.|  
|<xref:System.Xml.Serialization.XmlTypeAttribute>|Dichiarazioni di classe pubblica|Nome e spazio dei nomi del tipo XML.|  
  
 Oltre a questi attributi, tutti reperibili nello spazio dei nomi <xref:System.Xml.Serialization>, a un campo può essere anche applicato l'attributo <xref:System.ComponentModel.DefaultValueAttribute>. **DefaultValueAttribute** imposta il valore che verrà automaticamente assegnato al membro se non viene specificato alcun valore.  
  
 Per controllare la serializzazione XML con codifica SOAP, vedere [Attributi che controllano la serializzazione con codifica SOAP](attributes-that-control-encoded-soap-serialization.md).  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Controllo della serializzazione XML mediante attributi](controlling-xml-serialization-using-attributes.md)
- [Procedura: specificare un nome di elemento alternativo per un flusso XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
