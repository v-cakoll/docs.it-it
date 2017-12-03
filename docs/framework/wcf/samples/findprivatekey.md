---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ca357ccdcbe76f36f3ba56caf2013a80143728
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="56584-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="56584-102">FindPrivateKey</span></span>
<span data-ttu-id="56584-103">Può essere difficile individuare il percorso e il nome del file di chiave privata associati a un certificato X.509 specifico nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="56584-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="56584-104">Lo strumento FindPrivateKey.exe facilita questo processo.</span><span class="sxs-lookup"><span data-stu-id="56584-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56584-105">FindPrivateKey è un esempio che deve essere compilato prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="56584-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="56584-106">Vedere la sezione "per compilare il progetto FindPrivateKey" di seguito per istruzioni su come compilare lo strumento FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="56584-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="56584-107">I certificati X.509 vengono installati da un amministratore o da qualsiasi utente nel computer.</span><span class="sxs-lookup"><span data-stu-id="56584-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="56584-108">Tuttavia è possibile accedere al certificato da un servizio in esecuzione con un account diverso (ad esempio, ASPNET su [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o gli account Servizio di rete su [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="56584-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="56584-109">Questo account può non avere accesso al file di chiave privata se il certificato non è stato originariamente installato.</span><span class="sxs-lookup"><span data-stu-id="56584-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="56584-110">Lo strumento FindPrivateKey fornisce il percorso del file di chiave privata di un determinato certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="56584-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="56584-111">È possibile aggiungere o rimuovere autorizzazioni quando si conosce il percorso del file di chiave privata degli specifici certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="56584-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="56584-112">Negli esempi in cui vengono utilizzati i certificati per la sicurezza, si adopera lo strumento FindPrivateKey nel file Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="56584-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="56584-113">Dopo aver individuato il file di chiave privata, è possibile utilizzare gli altri strumenti quali Cacls.exe per impostare i diritti di accesso appropriati sul file.</span><span class="sxs-lookup"><span data-stu-id="56584-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="56584-114">Quando si esegue un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con un account utente, ad esempio un file eseguibile indipendente, accertarsi che l'account utente dispone dell'accesso in sola lettura al file.</span><span class="sxs-lookup"><span data-stu-id="56584-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="56584-115">Se si esegue servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in Internet Information Services (IIS), gli account predefiniti utilizzati per eseguire il servizio sono ASPNET in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o Servizio di rete su [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], che per impostazione predefinita non ha accesso al file di chiave privata.</span><span class="sxs-lookup"><span data-stu-id="56584-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56584-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="56584-116">Examples</span></span>  
 <span data-ttu-id="56584-117">Quando si accede a un certificato per il quale il processo dispone del privilegio di lettura, viene visualizzato un messaggio di eccezione simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56584-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="56584-118">Quando si verifica questo problema, utilizzare lo strumento FindPrivateKey per cercare il file di chiave privata e quindi impostare il diritto di accesso per il processo in cui è in esecuzione il servizio.</span><span class="sxs-lookup"><span data-stu-id="56584-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="56584-119">Ad esempio, questa operazione può essere eseguita con lo strumento Cacls.exe, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="56584-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="56584-120">Per compilare il progetto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="56584-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="56584-121">Aprire [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], quindi spostarsi nella sottodirectory specifica del linguaggio nel percorso della directory in cui si è installato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="56584-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="56584-122">Fare doppio clic sull'icona del file con estensione sln per aprirlo in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="56584-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="56584-123">Nel **compilare** dal menu **Ricompila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="56584-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="56584-124">I file di programma client vengono compilati in client\bin, mentre i file del programma del servizio vengono compilati in service\bin.</span><span class="sxs-lookup"><span data-stu-id="56584-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="56584-125">La compilazione della soluzione genera il file FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="56584-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="56584-126">Convenzioni: voci della riga di comando</span><span class="sxs-lookup"><span data-stu-id="56584-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="56584-127">"[*opzione*]" rappresenta un insieme facoltativo di parametri.</span><span class="sxs-lookup"><span data-stu-id="56584-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="56584-128">"{*opzione*}" rappresenta un set di parametri obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="56584-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="56584-129">"*opzione1* &#124; *opzione2*"rappresenta una scelta tra set di opzioni.</span><span class="sxs-lookup"><span data-stu-id="56584-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="56584-130">"\<*valore*>" rappresenta un valore di parametro da immettere.</span><span class="sxs-lookup"><span data-stu-id="56584-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="56584-131">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="56584-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="56584-132">Dove:</span><span class="sxs-lookup"><span data-stu-id="56584-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="56584-133">Se non è specificato alcun parametro nel prompt dei comandi, viene visualizzato questo testo della Guida.</span><span class="sxs-lookup"><span data-stu-id="56584-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="56584-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="56584-134">Examples</span></span>  
 <span data-ttu-id="56584-135">In questo esempio viene ricercato il nome del file del certificato con un nome soggetto "CN=localhost", nell'archivio Personale di Current User.FindPrivateKey My CurrentUser - n "CN=localhost".</span><span class="sxs-lookup"><span data-stu-id="56584-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="56584-136">In questo esempio viene ricercato il nome del file del certificato con un nome soggetto "CN=localhost", nell'archivio Personale dell'utente corrente e viene generato il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="56584-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="56584-137">In questo esempio viene ricercato il nome del file del certificato con un'identificazione digitale di "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", nell'archivio Personale del computer locale.</span><span class="sxs-lookup"><span data-stu-id="56584-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="56584-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56584-138">See Also</span></span>
