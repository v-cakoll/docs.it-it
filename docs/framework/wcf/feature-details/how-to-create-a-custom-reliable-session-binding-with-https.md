---
title: "Procedura: Creare un'associazione di sessione affidabile personalizzata con HTTPS"
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 7f22eeaae39b4d9a83c77c7f3e9db1d7d3f04e8e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895190"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="91472-102">Procedura: Creare un'associazione di sessione affidabile personalizzata con HTTPS</span><span class="sxs-lookup"><span data-stu-id="91472-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="91472-103">In questo argomento viene illustrato l'uso della protezione del trasporto SSL (Secure Sockets Layer) con sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="91472-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="91472-104">Per usare una sessione affidabile su HTTPS è necessario creare un'associazione personalizzata che usa una sessione affidabile e il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91472-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="91472-105">La sessione affidabile può essere abilitata in modo imperativo tramite codice o in modo dichiarativo nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91472-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="91472-106">Questa procedura usa i file di configurazione del client e del servizio per abilitare la sessione [ **\<** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) affidabile e l'elemento > di httpsTransport.</span><span class="sxs-lookup"><span data-stu-id="91472-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="91472-107">La parte principale di questa procedura è che l'  **\<endpoint >** elemento di configurazione contiene `bindingConfiguration` un attributo che fa riferimento a una configurazione `reliableSessionOverHttps`di binding personalizzata denominata.</span><span class="sxs-lookup"><span data-stu-id="91472-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="91472-108">[ **Il\<binding >** ](../../../../docs/framework/misc/binding.md) elemento di configurazione fa riferimento a questo nome per specificare che una sessione affidabile e il trasporto HTTPS vengono utilizzati includendo  **\<ReliableSession >** e **\<httpsTransport >** elementi.</span><span class="sxs-lookup"><span data-stu-id="91472-108">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="91472-109">Per la copia di origine di questo esempio, vedere [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span><span class="sxs-lookup"><span data-stu-id="91472-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="91472-110">Configurare il servizio con un CustomBinding per usare una sessione affidabile con HTTPS</span><span class="sxs-lookup"><span data-stu-id="91472-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="91472-111">Definire un contratto di servizio per il tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="91472-112">Implementare il contratto di servizio in una classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="91472-113">Si noti che le informazioni sull'indirizzo o sull'associazione non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="91472-114">Non è necessario scrivere codice per recuperare l'indirizzo o le informazioni di binding dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91472-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="91472-115">Creare un file *Web. config* per configurare un endpoint per `CalculatorService` con un'associazione personalizzata denominata `reliableSessionOverHttps` che utilizza una sessione affidabile e il trasporto HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91472-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="91472-116">Creare un file *Service. svc* contenente la riga:</span><span class="sxs-lookup"><span data-stu-id="91472-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="91472-117">Inserire il file *Service. svc* nella directory virtuale Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="91472-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="91472-118">Configurare il client con un CustomBinding per usare una sessione affidabile con HTTPS</span><span class="sxs-lookup"><span data-stu-id="91472-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="91472-119">Utilizzare lo [strumento ServiceModel Metadata Utility Tool (*Svcutil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dalla riga di comando per generare codice dai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="91472-120">Il client generato contiene l' `ICalculator` interfaccia che definisce il contratto di servizio che l'implementazione client deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="91472-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="91472-121">L'applicazione client generata contiene inoltre l'implementazione di `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="91472-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="91472-122">Si noti che le informazioni sull'indirizzo e sull'associazione non sono specificate nell'implementazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="91472-123">Non è necessario scrivere codice per recuperare l'indirizzo e le informazioni di binding dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91472-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="91472-124">Configurare un'associazione personalizzata denominata `reliableSessionOverHttps` per utilizzare il trasporto HTTPS e le sessioni affidabili.</span><span class="sxs-lookup"><span data-stu-id="91472-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="91472-125">Creare un'istanza di `ClientCalculator` in un'applicazione, quindi chiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="91472-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="91472-126">Compilare ed eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="91472-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="91472-127">.NET Framework (sicurezza)</span><span class="sxs-lookup"><span data-stu-id="91472-127">.NET Framework security</span></span>

<span data-ttu-id="91472-128">Poiché il certificato utilizzato in questo esempio è un certificato di prova creato con *Makecert. exe*, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo `https://localhost/servicemodelsamples/service.svc`HTTPS, ad esempio, dal browser.</span><span class="sxs-lookup"><span data-stu-id="91472-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="91472-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91472-129">See also</span></span>

- [<span data-ttu-id="91472-130">Sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="91472-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
