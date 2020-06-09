---
title: Creazione di un'intestazione personalizzata firmata e/o crittografata
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: 0adb4100bca1add2c23ff2c802ddb5e2cb1c368c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579658"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a>Creazione di un'intestazione personalizzata firmata e/o crittografata
Quando si chiama un servizio non WCF tramite un client WCF, è talvolta necessario usare intestazioni SOAP personalizzate. In WCF è presente un bug di canonizzazione che impedisce l'uso di intestazioni personalizzate firmate e crittografate con un servizio non WCF. Il problema è causato dalla canonizzazione errata degli spazi dei nomi XML predefiniti ed è significativo solo in caso di chiamata di servizi non WCF con intestazioni personalizzate firmate e/o crittografate.  Quando il servizio riceve il messaggio che contiene l'intestazione firmata e/o crittografata non è in grado di verificare la firma. Questa soluzione evita il bug di canonizzazione, consente l'interoperabilità con i servizi non WCF, ma non impedisce l'interoperabilità con i servizi WCF.  
  
## <a name="defining-the-custom-header"></a>Definizione dell'intestazione personalizzata  
 Le intestazioni personalizzate vengono definite creando un contratto di messaggio e contrassegnando i membri da inviare come intestazioni con un attributo <xref:System.ServiceModel.MessageHeaderAttribute>. Per risolvere il bug di canonizzazione, è necessario assicurarsi che il serializzatore XML dichiari lo spazio dei nomi per l'intestazione personalizzata con un prefisso anziché con una dichiarazione dello spazio dei nomi predefinita. Nel codice seguente viene mostrato come definire il tipo di dati che verrà usato come un'intestazione del messaggio con la dichiarazione dello spazio dei nomi corretta.  
  
```csharp
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 In questo codice viene dichiarato un nuovo tipo denominato `msgHeaderElement` che verrà serializzato tramite il serializzatore XML. Quando un'istanza di questo tipo viene serializzata, definirà uno spazio dei nomi con un prefisso 'h', risolvendo pertanto il bug di canonizzazione.  Il contratto di messaggio definirà quindi un'istanza di `msgHeaderElement` e la contrassegnerà con l'attributo <xref:System.ServiceModel.MessageHeaderAttribute> come illustrato nell'esempio seguente.  
  
```csharp
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Impostazione predefinita dei contratti di messaggio](../samples/default-message-contract.md)
- [Contratti di messaggio](../samples/message-contracts.md)
- [Utilizzo dei contratti di messaggio](using-message-contracts.md)
