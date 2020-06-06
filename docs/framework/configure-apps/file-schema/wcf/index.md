---
title: Schema di configurazione di WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 866b0639f4391e1898bbe36e458df87e3c24bfff
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77448659"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="a8cfc-102">Schema di configurazione di WCF</span><span class="sxs-lookup"><span data-stu-id="a8cfc-102">WCF Configuration Schema</span></span>
<span data-ttu-id="a8cfc-103">Gli elementi di configurazione Windows Communication Foundation (WCF) consentono di configurare il servizio WCF e le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="a8cfc-104">È possibile usare lo [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare i file di configurazione di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="a8cfc-105">Poiché i file di configurazione sono in formato XML, per modificarli manualmente usando un editor di testo è necessario avere familiarità con il linguaggio XML.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="a8cfc-106">In caso contrario, è possibile che si verifichino problemi. È ad esempio possibile che un tag di elemento XML o un attributo venga digitato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="a8cfc-107">Per i tag di elemento XML e gli attributi viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="a8cfc-108">Il sistema di configurazione WCF è basato sullo <xref:System.Configuration> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="a8cfc-109">È pertanto possibile usare tutte le funzionalità standard fornite dallo spazio dei nomi <xref:System.Configuration>, ad esempio il blocco, la crittografia e l'unione delle impostazioni di configurazione, allo scopo di aumentare la sicurezza dell'applicazione e della relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="a8cfc-110">Per altre informazioni su questi concetti, vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="a8cfc-111">[Crittografia delle informazioni di configurazione](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a8cfc-111">[Encrypting Configuration Information](https://docs.microsoft.com/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="a8cfc-112">[Blocco delle impostazioni di configurazione](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a8cfc-112">[Locking Configuration Settings](https://docs.microsoft.com/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="a8cfc-113">Questa sezione descrive tutti i valori possibili di ogni elemento di configurazione e le relative interazioni con gli altri elementi di configurazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="a8cfc-114">Nella mappa seguente viene illustrato lo schema di configurazione di WCF:</span><span class="sxs-lookup"><span data-stu-id="a8cfc-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![Diagramma che mostra lo schema di configurazione di WCF.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="a8cfc-116">È necessario proteggere le sezioni di configurazione di WCF nei file di configurazione dell'applicazione (app. config) con elenchi di controllo di accesso (ACL) appropriati per evitare potenziali minacce alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="a8cfc-117">Ad esempio, è necessario garantire che solo gli utenti appropriati siano in grado di accedere o apportare modifiche alla sezione del modello dei servizi del file di configurazione di un servizio o alle impostazioni di sicurezza relative alle associazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8cfc-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8cfc-118">In This Section</span></span>  
 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="a8cfc-119">Descrive l'elemento `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-119">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="a8cfc-120">Configura lo strumento SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-120">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="a8cfc-121">Descrive l'elemento di livello superiore per l'impostazione delle opzioni quando si usano serializzatori quali <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-121">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a8cfc-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a8cfc-122">Related Sections</span></span>  
 [<span data-ttu-id="a8cfc-123">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="a8cfc-123">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="a8cfc-124">Viene descritto come configurare i servizi e i client WCF.</span><span class="sxs-lookup"><span data-stu-id="a8cfc-124">Describes how to configure WCF services and clients.</span></span>
