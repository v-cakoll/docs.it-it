---
title: Esempio di FindPrivateKey - WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 72e2f49ae7c39b4a0486ec053ff1164c2d833cbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990093"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="333e8-102">Esempio FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="333e8-102">FindPrivateKey sample</span></span>

<span data-ttu-id="333e8-103">Può essere difficile individuare il percorso e il nome del file di chiave privata associati a un certificato X.509 specifico nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="333e8-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="333e8-104">Lo strumento FindPrivateKey.exe facilita questo processo.</span><span class="sxs-lookup"><span data-stu-id="333e8-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="333e8-105">FindPrivateKey è un esempio che deve essere compilato prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="333e8-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="333e8-106">Vedere le [per compilare il progetto FindPrivateKey](#to-build-the-findprivatekey-project) per istruzioni su come compilare lo strumento FindPrivateKey.</span><span class="sxs-lookup"><span data-stu-id="333e8-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="333e8-107">I certificati X.509 vengono installati da un amministratore o da qualsiasi utente nel computer.</span><span class="sxs-lookup"><span data-stu-id="333e8-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="333e8-108">Tuttavia, il certificato sono accessibili da un servizio in esecuzione con un account diverso.</span><span class="sxs-lookup"><span data-stu-id="333e8-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="333e8-109">Ad esempio, l'account del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="333e8-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="333e8-110">Questo account può non avere accesso al file di chiave privata se il certificato non è stato originariamente installato.</span><span class="sxs-lookup"><span data-stu-id="333e8-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="333e8-111">Lo strumento FindPrivateKey fornisce il percorso del file di chiave privata di un determinato certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="333e8-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="333e8-112">È possibile aggiungere o rimuovere autorizzazioni quando si conosce il percorso del file di chiave privata degli specifici certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="333e8-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="333e8-113">Gli esempi che usano certificati per la sicurezza utilizzano lo strumento FindPrivateKey nel *Setup. bat* file.</span><span class="sxs-lookup"><span data-stu-id="333e8-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="333e8-114">Una volta individuato il file di chiave privata, è possibile usare altri strumenti, ad esempio *Cacls.exe* per impostare i diritti di accesso appropriati sul file.</span><span class="sxs-lookup"><span data-stu-id="333e8-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="333e8-115">Quando si esegue un servizio Windows Communication Foundation (WCF) con un account utente, ad esempio un file eseguibile indipendente, assicurarsi che l'account utente disponga di accesso in lettura al file.</span><span class="sxs-lookup"><span data-stu-id="333e8-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="333e8-116">Quando si esegue un servizio WCF in Internet Information Services (IIS) gli account predefiniti quali viene eseguito il servizio sono il servizio di rete in IIS 7 e versioni precedenti, o identità Pool di applicazioni in IIS 7.5 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="333e8-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="333e8-117">Per altre informazioni, vedere [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="333e8-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="333e8-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="333e8-118">Examples</span></span>

<span data-ttu-id="333e8-119">Quando si accede a un certificato per il quale il processo non dispone di privilegi di lettura, viene visualizzato un messaggio di eccezione simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="333e8-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="333e8-120">In questo caso, utilizzare lo strumento FindPrivateKey per trovare il file di chiave privata e quindi impostare il diritto di accesso per il processo di cui è in esecuzione il servizio.</span><span class="sxs-lookup"><span data-stu-id="333e8-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="333e8-121">Ad esempio, questa operazione può essere eseguita con lo strumento Cacls.exe come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="333e8-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="333e8-122">Per compilare il progetto FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="333e8-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="333e8-123">Per scaricare il progetto, visitare [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="333e8-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="333e8-124">Aprire [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] e passare al *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* cartella nel percorso della directory in cui è installato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="333e8-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="333e8-125">Fare doppio clic sull'icona del file con estensione sln per aprirlo in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="333e8-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="333e8-126">Nel **compilare** dal menu **Ricompila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="333e8-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="333e8-127">La compilazione della soluzione genera il file: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="333e8-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="333e8-128">Convenzioni: voci della riga di comando</span><span class="sxs-lookup"><span data-stu-id="333e8-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="333e8-129">"[*opzione*]" rappresenta un set facoltativo di parametri.</span><span class="sxs-lookup"><span data-stu-id="333e8-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="333e8-130">"{*opzione*}" rappresenta un set di parametri obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="333e8-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="333e8-131">"*opzione1* &#124; *opzione2*" rappresenta una scelta tra set di opzioni.</span><span class="sxs-lookup"><span data-stu-id="333e8-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="333e8-132">"\<*valore*>" rappresenta un valore del parametro da immettere.</span><span class="sxs-lookup"><span data-stu-id="333e8-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="333e8-133">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="333e8-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="333e8-134">Dove:</span><span class="sxs-lookup"><span data-stu-id="333e8-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="333e8-135">Se viene specificato alcun parametro al prompt dei comandi, viene visualizzato il testo della Guida.</span><span class="sxs-lookup"><span data-stu-id="333e8-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="333e8-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="333e8-136">Examples</span></span>

<span data-ttu-id="333e8-137">In questo esempio viene ricercato il nome file del certificato con un nome soggetto "CN = localhost", nell'archivio personale dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="333e8-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="333e8-138">In questo esempio viene ricercato il nome file del certificato con un nome soggetto "CN = localhost", nel profilo personale archivio dell'utente corrente e il percorso completo della directory di output.</span><span class="sxs-lookup"><span data-stu-id="333e8-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="333e8-139">In questo esempio viene ricercato il nome del file del certificato con un'identificazione digitale di "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", nell'archivio Personale del computer locale.</span><span class="sxs-lookup"><span data-stu-id="333e8-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
