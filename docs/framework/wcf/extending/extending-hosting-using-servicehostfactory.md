---
title: Estensione dell'hosting tramite ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: de6a590b94285872dd77006eda7f86d5d629be9d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849911"
---
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="46dc2-102">Estensione dell'hosting tramite ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="46dc2-102">Extending Hosting Using ServiceHostFactory</span></span>
<span data-ttu-id="46dc2-103">L'API <xref:System.ServiceModel.ServiceHost> standard per i servizi di hosting in Windows Communication Foundation (WCF) è un punto di estensibilità nell'architettura WCF.</span><span class="sxs-lookup"><span data-stu-id="46dc2-103">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="46dc2-104">Gli utenti possono derivare proprie classi host da <xref:System.ServiceModel.ServiceHost>, in genere per eseguire l'override di <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening>, per usare <xref:System.ServiceModel.Description.ServiceDescription> al fine di aggiungere endpoint predefiniti in modo imperativo o modificare comportamenti, prima di aprire il servizio.</span><span class="sxs-lookup"><span data-stu-id="46dc2-104">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="46dc2-105">Nell'ambiente di self-hosting, non è necessario creare una classe <xref:System.ServiceModel.ServiceHost> personalizzata, perché si scrive il codice che crea un'istanza dell'host e quindi si chiama <xref:System.ServiceModel.ICommunicationObject.Open> sull'host dopo averne creato l'istanza.</span><span class="sxs-lookup"><span data-stu-id="46dc2-105">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="46dc2-106">Tra questi due passaggi è possibile eseguire tutte le operazioni che si desidera.</span><span class="sxs-lookup"><span data-stu-id="46dc2-106">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="46dc2-107">È ad esempio possibile aggiungere una nuova classe <xref:System.ServiceModel.Description.IServiceBehavior>:</span><span class="sxs-lookup"><span data-stu-id="46dc2-107">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="46dc2-108">Questo approccio non è riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="46dc2-108">This approach is not reusable.</span></span> <span data-ttu-id="46dc2-109">Il codice che modifica la descrizione è inserito nel programma host, in questo caso, la funzione Main(), ed è quindi difficile riutilizzare la logica in questione in altri contesti.</span><span class="sxs-lookup"><span data-stu-id="46dc2-109">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="46dc2-110">Esistono altri modi di aggiungere una classe <xref:System.ServiceModel.Description.IServiceBehavior> che non richiedono codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="46dc2-110">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="46dc2-111">È possibile derivare un attributo da <xref:System.ServiceModel.ServiceBehaviorAttribute> e inserirlo sul tipo di implementazione del servizio o è possibile rendere configurabile un comportamento personalizzato e comporlo dinamicamente usando la configurazione.</span><span class="sxs-lookup"><span data-stu-id="46dc2-111">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="46dc2-112">Tuttavia, per risolvere il problema, è possibile usare anche una leggera variazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="46dc2-112">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="46dc2-113">Un approccio consiste nello spostare il codice che aggiunge ServiceBehavior fuori da `Main()` e inserirlo nel metodo <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> di un derivato personalizzato di <xref:System.ServiceModel.ServiceHost>:</span><span class="sxs-lookup"><span data-stu-id="46dc2-113">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 <span data-ttu-id="46dc2-114">All'interno di `Main()` è quindi possibile usare:</span><span class="sxs-lookup"><span data-stu-id="46dc2-114">Then, inside of `Main()` you can use:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="46dc2-115">Ora è stata incapsulata la logica personalizzata in un'astrazione pulita, facilmente riutilizzabile su molti eseguibili host diversi.</span><span class="sxs-lookup"><span data-stu-id="46dc2-115">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="46dc2-116">Non è immediatamente ovvio come usare questa classe <xref:System.ServiceModel.ServiceHost> personalizzata da Internet Information Services (IIS) o dal servizio di attivazione dei processi di Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="46dc2-116">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="46dc2-117">Questi ambienti sono diversi dall'ambiente di self-hosting, perché l'ambiente host è quello che crea l'istanza di <xref:System.ServiceModel.ServiceHost> per conto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="46dc2-117">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="46dc2-118">L'infrastruttura di hosting di IIS e WAS non conosce assolutamente il derivato <xref:System.ServiceModel.ServiceHost> personalizzato.</span><span class="sxs-lookup"><span data-stu-id="46dc2-118">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="46dc2-119">La classe <xref:System.ServiceModel.Activation.ServiceHostFactory> è stata progettata per risolvere questo problema di accesso alla classe <xref:System.ServiceModel.ServiceHost> personalizzata da IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="46dc2-119">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="46dc2-120">Poiché un host personalizzato derivato da <xref:System.ServiceModel.ServiceHost> viene configurato dinamicamente ed è potenzialmente di vario tipo, l'ambiente host non ne crea mai un'istanza in modo diretto.</span><span class="sxs-lookup"><span data-stu-id="46dc2-120">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="46dc2-121">WCF utilizza invece un modello factory per fornire un livello di riferimento indiretto tra l'ambiente host e il tipo concreto del servizio.</span><span class="sxs-lookup"><span data-stu-id="46dc2-121">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="46dc2-122">Se non diversamente detto, usa un'implementazione predefinita di <xref:System.ServiceModel.Activation.ServiceHostFactory> che restituisce un'istanza di <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="46dc2-122">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="46dc2-123">Tuttavia, è anche possibile fornire una factory personalizzata che restituisca l'host derivato specificando il nome del tipo CLR dell'implementazione factory @ServiceHost nella direttiva.</span><span class="sxs-lookup"><span data-stu-id="46dc2-123">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="46dc2-124">Nei casi di base, l'implementazione di una propria factory dovrebbe essere un esercizio semplice.</span><span class="sxs-lookup"><span data-stu-id="46dc2-124">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="46dc2-125">Di seguito è ad esempio riportata una classe <xref:System.ServiceModel.Activation.ServiceHostFactory> personalizzata che restituisce una classe <xref:System.ServiceModel.ServiceHost> derivata:</span><span class="sxs-lookup"><span data-stu-id="46dc2-125">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="46dc2-126">Per usare questa factory anziché la factory predefinita, fornire il nome del tipo nella @ServiceHost direttiva, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="46dc2-126">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 <span data-ttu-id="46dc2-127">Sebbene non ci siano limiti tecnici a ciò che è possibile fare alla classe <xref:System.ServiceModel.ServiceHost> restituita da <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, è consigliabile mantenere l'implementazione della factory quanto più semplice è possibile.</span><span class="sxs-lookup"><span data-stu-id="46dc2-127">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="46dc2-128">Se si dispone di un numero elevato di logica personalizzata, è preferibile inserire tale logica all'interno dell'host anziché nella Factory, in modo che possa essere riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="46dc2-128">If you have lots of custom logic, it is better to put that logic inside of your host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="46dc2-129">Esiste un ulteriore livello dell'API di hosting che dovrebbe essere qui citato.</span><span class="sxs-lookup"><span data-stu-id="46dc2-129">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="46dc2-130">WCF dispone <xref:System.ServiceModel.ServiceHostBase> anche di <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>e, da <xref:System.ServiceModel.ServiceHost> cui <xref:System.ServiceModel.Activation.ServiceHostFactory> derivano rispettivamente e.</span><span class="sxs-lookup"><span data-stu-id="46dc2-130">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="46dc2-131">Queste classi sono destinate a scenari più avanzati, in cui è necessario scambiare ampie parti del sistema dei metadati con proprie creazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="46dc2-131">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
