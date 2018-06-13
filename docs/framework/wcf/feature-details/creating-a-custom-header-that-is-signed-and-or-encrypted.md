---
title: Creazione di un'intestazione personalizzata che viene firmata e- o crittografati
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: 4770d650cba5c182aa56d9ac7afa39e585512d4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490695"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="1054a-102">Creazione di un'intestazione personalizzata che viene firmata e- o crittografati</span><span class="sxs-lookup"><span data-stu-id="1054a-102">Creating a custom header that is signed and-or encrypted</span></span>
<span data-ttu-id="1054a-103">Quando si chiama un servizio non WCF tramite un client WCF, è talvolta necessario usare intestazioni SOAP personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1054a-103">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="1054a-104">In WCF è presente un bug di canonizzazione che impedisce l'uso di intestazioni personalizzate firmate e crittografate con un servizio non WCF.</span><span class="sxs-lookup"><span data-stu-id="1054a-104">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="1054a-105">Il problema è causato dalla canonizzazione errata degli spazi dei nomi XML predefiniti</span><span class="sxs-lookup"><span data-stu-id="1054a-105">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="1054a-106">ed è significativo solo in caso di chiamata di servizi non WCF con intestazioni personalizzate firmate e/o crittografate.</span><span class="sxs-lookup"><span data-stu-id="1054a-106">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="1054a-107">Quando il servizio riceve il messaggio che contiene l'intestazione firmata e/o crittografata non è in grado di verificare la firma.</span><span class="sxs-lookup"><span data-stu-id="1054a-107">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="1054a-108">Questa soluzione evita il bug di canonizzazione, consente l'interoperabilità con i servizi non WCF, ma non impedisce l'interoperabilità con i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="1054a-108">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="1054a-109">Definizione dell'intestazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="1054a-109">Defining the custom header</span></span>  
 <span data-ttu-id="1054a-110">Le intestazioni personalizzate vengono definite creando un contratto di messaggio e contrassegnando i membri da inviare come intestazioni con un attributo <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1054a-110">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="1054a-111">Per risolvere il bug di canonizzazione, è necessario assicurarsi che il serializzatore XML dichiari lo spazio dei nomi per l'intestazione personalizzata con un prefisso anziché con una dichiarazione dello spazio dei nomi predefinita.</span><span class="sxs-lookup"><span data-stu-id="1054a-111">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="1054a-112">Nel codice seguente viene mostrato come definire il tipo di dati che verrà usato come un'intestazione del messaggio con la dichiarazione dello spazio dei nomi corretta.</span><span class="sxs-lookup"><span data-stu-id="1054a-112">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
```  
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
  
 <span data-ttu-id="1054a-113">In questo codice viene dichiarato un nuovo tipo denominato `msgHeaderElement` che verrà serializzato tramite il serializzatore XML.</span><span class="sxs-lookup"><span data-stu-id="1054a-113">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="1054a-114">Quando un'istanza di questo tipo viene serializzata, definirà uno spazio dei nomi con un prefisso 'h', risolvendo pertanto il bug di canonizzazione.</span><span class="sxs-lookup"><span data-stu-id="1054a-114">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="1054a-115">Il contratto di messaggio definirà quindi un'istanza di `msgHeaderElement` e la contrassegnerà con l'attributo <xref:System.ServiceModel.MessageHeaderAttribute> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1054a-115">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1054a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1054a-116">See Also</span></span>  
 [<span data-ttu-id="1054a-117">Impostazione predefinita dei contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="1054a-117">Default Message Contract</span></span>](../../../../docs/framework/wcf/samples/default-message-contract.md)  
 [<span data-ttu-id="1054a-118">Contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="1054a-118">Message Contracts</span></span>](../../../../docs/framework/wcf/samples/message-contracts.md)  
 [<span data-ttu-id="1054a-119">Uso di contratti di messaggio</span><span class="sxs-lookup"><span data-stu-id="1054a-119">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
