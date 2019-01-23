---
title: "Procedura: Creare un'associazione di sessione affidabile personalizzata con HTTPS"
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516681"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="fa673-102">Procedura: Creare un'associazione di sessione affidabile personalizzata con HTTPS</span><span class="sxs-lookup"><span data-stu-id="fa673-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="fa673-103">In questo argomento viene illustrato l'uso della protezione del trasporto SSL (Secure Sockets Layer) con sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="fa673-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="fa673-104">Per usare una sessione affidabile su HTTPS è necessario creare un'associazione personalizzata che usa una sessione affidabile e il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fa673-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="fa673-105">La sessione affidabile è abilitare in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa673-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="fa673-106">Questa procedura Usa i file di configurazione client e servizio per attivare la sessione affidabile e il [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="fa673-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="fa673-107">La parte principale di questa procedura è che il  **\<endpoint >** elemento di configurazione contengono una `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione personalizzata denominata `reliableSessionOverHttps`.</span><span class="sxs-lookup"><span data-stu-id="fa673-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="fa673-108">Il [  **\<associazione >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa riferimento a questo nome per specificare che vengono usati una sessione affidabile e il trasporto HTTPS, includendo  **\< reliableSession >** e  **\<httpsTransport >** elementi.</span><span class="sxs-lookup"><span data-stu-id="fa673-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="fa673-109">Per la copia di origine di questo esempio, vedere [Custom Binding sessione affidabile su HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="fa673-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="fa673-110">Configurare il servizio con una CustomBinding per usare una sessione affidabile con HTTPS</span><span class="sxs-lookup"><span data-stu-id="fa673-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="fa673-111">Definire un contratto di servizio per il tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="fa673-112">Implementare il contratto di servizio in una classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="fa673-113">Si noti che le informazioni di indirizzo o il binding non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fa673-114">Non è necessario scrivere codice per recuperare le informazioni di indirizzo o il binding dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa673-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="fa673-115">Creare un *Web. config* file per configurare un endpoint per il `CalculatorService` con un'associazione personalizzata denominata `reliableSessionOverHttps` che usa una sessione affidabile e il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fa673-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="fa673-116">Creare un *Service. svc* file che contiene la riga:</span><span class="sxs-lookup"><span data-stu-id="fa673-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="fa673-117">Sul posto di *Service. svc* file nella directory virtuale di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="fa673-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="fa673-118">Configurare il client con una CustomBinding per usare una sessione affidabile con HTTPS</span><span class="sxs-lookup"><span data-stu-id="fa673-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="fa673-119">Usare la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="fa673-120">Il client generato contiene le `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="fa673-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="fa673-121">L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="fa673-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="fa673-122">Si noti che le informazioni di associazione e indirizzo non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="fa673-123">Non è necessario scrivere codice per recuperare le informazioni di indirizzo e binding dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa673-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="fa673-124">Configurare un'associazione personalizzata denominata `reliableSessionOverHttps` usare il trasporto HTTPS e sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="fa673-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="fa673-125">Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="fa673-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="fa673-126">Compilare ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="fa673-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="fa673-127">.NET Framework (sicurezza)</span><span class="sxs-lookup"><span data-stu-id="fa673-127">.NET Framework security</span></span>

<span data-ttu-id="fa673-128">Poiché il certificato usato in questo esempio è un certificato di prova creato con *Makecert.exe*, viene visualizzato un avviso di sicurezza quando si tenta di accedere, ad esempio un indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc`, dal browser.</span><span class="sxs-lookup"><span data-stu-id="fa673-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa673-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa673-129">See also</span></span>

- [<span data-ttu-id="fa673-130">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="fa673-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
