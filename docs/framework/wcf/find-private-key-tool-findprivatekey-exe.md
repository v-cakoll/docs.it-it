---
title: Ricerca dello strumento di chiave privata (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="b0f0a-102">Ricerca dello strumento di chiave privata (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="b0f0a-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="b0f0a-103">Questo strumento da riga di comando può essere usato per recuperare una chiave privata da un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="b0f0a-104">Ad esempio, *FindPrivateKey.exe* può essere utilizzato per trovare il percorso e il nome del file di chiave privato associato a un certificato x. 509 specifico nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0f0a-105">Lo strumento FindPrivateKey viene fornito come esempio WCF.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="b0f0a-106">Per ulteriori informazioni su dove trovare il codice di esempio e come compilarlo, vedere [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="b0f0a-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="b0f0a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0f0a-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="b0f0a-108">Note</span><span class="sxs-lookup"><span data-stu-id="b0f0a-108">Remarks</span></span>

<span data-ttu-id="b0f0a-109">Nelle tabelle seguenti vengono descritti gli argomenti e le opzioni che possono essere usati con lo strumento di Ricerca della Chiave Privata (FindPrivateKey.exe).</span><span class="sxs-lookup"><span data-stu-id="b0f0a-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="b0f0a-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="b0f0a-110">Argument</span></span>|<span data-ttu-id="b0f0a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0f0a-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="b0f0a-112">Nome dell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="b0f0a-113">Percorso dell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="b0f0a-114">Opzione</span><span class="sxs-lookup"><span data-stu-id="b0f0a-114">Option</span></span>|<span data-ttu-id="b0f0a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0f0a-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="b0f0a-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="b0f0a-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="b0f0a-117">Specifica il nome dell’oggetto del certificato.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="b0f0a-118">`/t <`*identificazione personale*`>`</span><span class="sxs-lookup"><span data-stu-id="b0f0a-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="b0f0a-119">Specifica l'identificazione digitale del certificato.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="b0f0a-120">Usare Certmgr.exe per recuperare l'identificazione digitale del certificato.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="b0f0a-121">Restituisce soltanto il nome file.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="b0f0a-122">Restituisce soltanto la directory.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="b0f0a-123">Restituisce il nome file assoluto.</span><span class="sxs-lookup"><span data-stu-id="b0f0a-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="b0f0a-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="b0f0a-124">Examples</span></span>

<span data-ttu-id="b0f0a-125">Il seguente comando recupera la chiave privata per John Doe:</span><span class="sxs-lookup"><span data-stu-id="b0f0a-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="b0f0a-126">Il seguente comando recupera la chiave privata per il computer locale:</span><span class="sxs-lookup"><span data-stu-id="b0f0a-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```