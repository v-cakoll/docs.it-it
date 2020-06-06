---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399533"
---
# \<soapProcessing>

<span data-ttu-id="3cfee-101">Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.</span><span class="sxs-lookup"><span data-stu-id="3cfee-101">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a><span data-ttu-id="3cfee-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cfee-102">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cfee-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3cfee-103">Attributes and elements</span></span>  
  
<span data-ttu-id="3cfee-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3cfee-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cfee-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="3cfee-105">Attributes</span></span>  
  
|                   | <span data-ttu-id="3cfee-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cfee-106">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="3cfee-107">Valore booleano che specifica se è necessario effettuare il marshalling dei messaggi tra le versioni di messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="3cfee-107">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3cfee-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3cfee-108">Child elements</span></span>

<span data-ttu-id="3cfee-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="3cfee-109">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3cfee-110">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3cfee-110">Parent elements</span></span>

|     | <span data-ttu-id="3cfee-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cfee-111">Description</span></span> |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | <span data-ttu-id="3cfee-112">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="3cfee-112">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3cfee-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="3cfee-113">Remarks</span></span>

<span data-ttu-id="3cfee-114">L'elaborazione SOAP è il processo in cui i messaggi vengono convertiti tra le versioni dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3cfee-114">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="3cfee-115">Il servizio di routing Windows Communication Foundation (WCF) può convertire i messaggi da un protocollo a un altro.</span><span class="sxs-lookup"><span data-stu-id="3cfee-115">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="3cfee-116">Se le versioni del messaggio in ingresso e in uscita sono diverse, viene creato un nuovo messaggio della versione corretta.</span><span class="sxs-lookup"><span data-stu-id="3cfee-116">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="3cfee-117">L'elaborazione di messaggi da un oggetto <xref:System.ServiceModel.Channels.MessageVersion> a un altro viene eseguita costruendo un nuovo messaggio WCF contenente la parte del corpo e le relative intestazioni dal messaggio WCF in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3cfee-117">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="3cfee-118">Le intestazioni specifiche dell'indirizzamento o quelle riconosciute al livello del router non vengono usate durante la costruzione del nuovo messaggio WCF, poiché queste intestazioni presentano una versione diversa (nel caso delle intestazioni di indirizzamento) o sono state elaborate come parte della comunicazione tra il client e il router.</span><span class="sxs-lookup"><span data-stu-id="3cfee-118">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="3cfee-119">Il posizionamento di un'intestazione nel messaggio in uscita viene determinato dal fatto che essa venga contrassegnata o meno come riconosciuta quando è passata attraverso il livello del canale in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3cfee-119">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="3cfee-120">Le intestazioni non riconosciute (ad esempio le intestazioni personalizzate) non vengono rimosse e passano pertanto attraverso il servizio di routing mediante copia nel messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="3cfee-120">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="3cfee-121">Il corpo del messaggio viene copiato nel messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="3cfee-121">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="3cfee-122">Il messaggio viene quindi inviato al canale di uscita al quale puntano tutte le intestazioni e verranno creati e aggiunti gli altri dati di envelope specifici di tale protocollo/trasporto di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="3cfee-122">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="3cfee-123">Questi passaggi di elaborazione vengono eseguiti quando il comportamento di elaborazione SOAP è specificato.</span><span class="sxs-lookup"><span data-stu-id="3cfee-123">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="3cfee-124">Questo [\<soapProcessingExtension>](soapprocessing.md) comportamento è un comportamento dell'endpoint applicato a tutti gli endpoint client (in uscita) all'avvio del servizio di routing.</span><span class="sxs-lookup"><span data-stu-id="3cfee-124">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="3cfee-125">per impostazione predefinita, il [\<routing>](routing-of-servicebehavior.md) comportamento crea e associa un nuovo [\<soapProcessingExtension>](soapprocessing.md) comportamento con `processMessages` impostato su `true` per ogni endpoint client.</span><span class="sxs-lookup"><span data-stu-id="3cfee-125">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="3cfee-126">Se si dispone di un protocollo che il servizio di routing non interpreta o si desidera eseguire l'override del comportamento di elaborazione predefinito, è possibile disabilitare l'elaborazione SOAP per l'intero servizio di routing o solo per determinati endpoint.</span><span class="sxs-lookup"><span data-stu-id="3cfee-126">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="3cfee-127">Per disabilitare l'elaborazione SOAP per l'intero servizio di routing su tutti gli endpoint, impostare l' `soapProcessing` attributo del [\<routing>](routing-of-servicebehavior.md) comportamento su `false` .</span><span class="sxs-lookup"><span data-stu-id="3cfee-127">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="3cfee-128">Per disattivare l'elaborazione SOAP per un determinato endpoint, utilizzare questo comportamento e impostare l'attributo `processMessages` su `false`, quindi collegare questo comportamento all'endpoint che non si desidera venga eseguito con il codice di elaborazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="3cfee-128">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="3cfee-129">Quando il [\<routing>](routing-of-servicebehavior.md) comportamento configura il servizio di routing, la riapplicazione del comportamento dell'endpoint verrà ignorata perché ne esiste già una.</span><span class="sxs-lookup"><span data-stu-id="3cfee-129">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
