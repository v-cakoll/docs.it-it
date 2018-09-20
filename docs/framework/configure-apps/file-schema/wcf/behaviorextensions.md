---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: d025497956715913923e839cb6c482f44f96babb
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320708"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="26d80-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="26d80-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="26d80-103">Le estensioni di comportamento consentono all'utente di creare elementi di comportamento definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="26d80-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="26d80-104">Questi elementi possono essere usati insieme agli elementi di comportamento standard di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="26d80-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="26d80-105">Nella sezione `behaviorExtensions` l'elemento viene definito in modo tale che possa essere usato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="26d80-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="26d80-106">Di seguito viene fornito l'esempio di una tipica estensione di comportamento.</span><span class="sxs-lookup"><span data-stu-id="26d80-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="26d80-107">Per aggiungere capacità di configurazione all'elemento è necessario scrivere e registrare un elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="26d80-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="26d80-108">Per altre informazioni a tal proposito, vedere la documentazione di <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="26d80-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="26d80-109">Dopo che l'elemento e il relativo tipo di configurazione sono stati definiti, è possibile usare l'estensione come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26d80-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="26d80-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="26d80-110">Security</span></span>  
 <span data-ttu-id="26d80-111">È consigliato fortemente l'uso di nomi di assembly completi per la registrazione di tipi nei file `machine.config` e `app.config`.</span><span class="sxs-lookup"><span data-stu-id="26d80-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="26d80-112">Se il tipo non è definito in modo univoco, il caricatore dei tipi CLR lo cerca nei percorsi seguenti nell'ordine specificato:</span><span class="sxs-lookup"><span data-stu-id="26d80-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="26d80-113">Se l'assembly del tipo è conosciuto, il caricatore esegue una ricerca nei percorsi di reindirizzamento del file di configurazione, in GAC, nell'assembly corrente usando le informazioni di configurazione e la directory base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26d80-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="26d80-114">Se l'assembly è sconosciuto, il caricatore esegue una ricerca nell'assembly corrente, in mscorlib e nel percorso restituito dal gestore eventi `TypeResolve`.</span><span class="sxs-lookup"><span data-stu-id="26d80-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="26d80-115">Questo ordine di ricerca CLR può essere modificato con hook quali il meccanismo di inoltro dei tipi e l'evento AppDomain.TypeResolve.</span><span class="sxs-lookup"><span data-stu-id="26d80-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="26d80-116">Un autore di un attacco può sfruttare l'ordine di ricerca CLR ed eseguire codice non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="26d80-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="26d80-117">L'uso di nomi univoci completi (sicuri) identifica un tipo e aumenta ulteriormente la sicurezza del sistema.</span><span class="sxs-lookup"><span data-stu-id="26d80-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="26d80-118">Per altre informazioni, vedere [modo in cui il Runtime individua gli assembly](https://go.microsoft.com/fwlink/?LinkId=95336) e <xref:System.AppDomain.TypeResolve>.</span><span class="sxs-lookup"><span data-stu-id="26d80-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d80-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26d80-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="26d80-120">Configurazione ed estensione del runtime con i comportamenti</span><span class="sxs-lookup"><span data-stu-id="26d80-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
