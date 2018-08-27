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
ms.openlocfilehash: 07c4c1e9b9a9da2e9a585efdcac644c616012078
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934394"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Attributi per il controllo della serializzazione SOAP codificata

Il documento del World Wide Web Consortium (W3C) denominato [SOAP Simple Object Access Protocol () 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contiene una sezione facoltativa (sezione 5) che descrive la modalità di codifica dei parametri SOAP. Per ottenere la conformità alla sezione 5 delle specifiche, è necessario usare un set speciale di attributi reperibile nello spazio dei nomi <xref:System.Xml.Serialization>. Applicare tali attributi nel modo appropriato alle classi e ai membri delle classi, quindi utilizzare <xref:System.Xml.Serialization.XmlSerializer> per serializzare le istanze della classe o delle classi.

Nella seguente tabella sono illustrati gli attributi, dove è possibile applicarli e la loro funzione. Per altre informazioni sull'utilizzo di questi attributi per il controllo della serializzazione XML, vedere [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) e [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](how-to-override-encoded-soap-xml-serialization.md).

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

[Serializzazione SOAP e XML](xml-and-soap-serialization.md)  
[Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
[Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](how-to-override-encoded-soap-xml-serialization.md)  
[Attributi](../../../docs/standard/attributes/index.md)  
<xref:System.Xml.Serialization.XmlSerializer>  
[Procedura: Serializzare un oggetto](how-to-serialize-an-object.md)  
[Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)