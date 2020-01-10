---
title: 'Procedura: accedere ai dispositivi di crittografia hardware'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: d6ee22fd9fb0c11e22ac01ff83b3269e37e37763
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706175"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="82c34-102">Procedura: accedere ai dispositivi di crittografia hardware</span><span class="sxs-lookup"><span data-stu-id="82c34-102">How to: Access Hardware Encryption Devices</span></span>
<span data-ttu-id="82c34-103">È possibile usare la classe <xref:System.Security.Cryptography.CspParameters> per accedere ai dispositivi di crittografia hardware.</span><span class="sxs-lookup"><span data-stu-id="82c34-103">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="82c34-104">Questa classe può essere usata, ad esempio, per integrare l'applicazione in uso con una smart card, un generatore di numeri casuali hardware o per l'implementazione hardware di un determinato algoritmo di crittografia.</span><span class="sxs-lookup"><span data-stu-id="82c34-104">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  
  
 <span data-ttu-id="82c34-105">La classe <xref:System.Security.Cryptography.CspParameters> crea un provider del servizio di crittografia (CSP, Cryptographic Service Provider) che accede a un dispositivo di crittografia hardware installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="82c34-105">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="82c34-106">È possibile verificare la disponibilità di un CSP esaminando la chiave del Registro di sistema (Regedit.exe): HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="82c34-106">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="82c34-107">Per firmare i dati mediante una scheda di chiavi</span><span class="sxs-lookup"><span data-stu-id="82c34-107">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="82c34-108">Creare una nuova istanza della classe <xref:System.Security.Cryptography.CspParameters>, passando il tipo di provider integer e il nome del provider al costruttore.</span><span class="sxs-lookup"><span data-stu-id="82c34-108">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="82c34-109">Passare i flag appropriati alla proprietà <xref:System.Security.Cryptography.CspParameters.Flags%2A> dell'oggetto <xref:System.Security.Cryptography.CspParameters> appena creato.</span><span class="sxs-lookup"><span data-stu-id="82c34-109">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="82c34-110">Passare, ad esempio, il flag <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.</span><span class="sxs-lookup"><span data-stu-id="82c34-110">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="82c34-111">Creare una nuova istanza di una classe <xref:System.Security.Cryptography.AsymmetricAlgorithm> (ad esempio, la classe <xref:System.Security.Cryptography.RSACryptoServiceProvider>), passando l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore.</span><span class="sxs-lookup"><span data-stu-id="82c34-111">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="82c34-112">Firmare i dati mediante uno dei metodi `Sign` e verificarli mediante uno dei metodi `Verify`.</span><span class="sxs-lookup"><span data-stu-id="82c34-112">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="82c34-113">Per generare un numero casuale usando un generatore di numeri casuali hardware</span><span class="sxs-lookup"><span data-stu-id="82c34-113">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="82c34-114">Creare una nuova istanza della classe <xref:System.Security.Cryptography.CspParameters>, passando il tipo di provider integer e il nome del provider al costruttore.</span><span class="sxs-lookup"><span data-stu-id="82c34-114">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="82c34-115">Creare una nuova istanza della classe <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passando l'oggetto <xref:System.Security.Cryptography.CspParameters> al costruttore.</span><span class="sxs-lookup"><span data-stu-id="82c34-115">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="82c34-116">Creare un valore casuale usando il metodo <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> o <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.</span><span class="sxs-lookup"><span data-stu-id="82c34-116">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82c34-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="82c34-117">Example</span></span>  
 <span data-ttu-id="82c34-118">L'esempio di codice seguente illustra come firmare i dati mediante una smart card.</span><span class="sxs-lookup"><span data-stu-id="82c34-118">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="82c34-119">L'esempio di codice crea un oggetto <xref:System.Security.Cryptography.CspParameters> che espone una smart card, quindi inizializza un oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> mediante il CSP</span><span class="sxs-lookup"><span data-stu-id="82c34-119">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="82c34-120">e infine firma e verifica alcuni dati.</span><span class="sxs-lookup"><span data-stu-id="82c34-120">The code example then signs and verifies some data.</span></span>  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82c34-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="82c34-121">Compiling the Code</span></span>  
  
- <span data-ttu-id="82c34-122">Includere gli spazi dei nomi <xref:System> e <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="82c34-122">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="82c34-123">È necessario avere un lettore di smart card e driver installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="82c34-123">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="82c34-124">È necessario inizializzare l'oggetto <xref:System.Security.Cryptography.CspParameters> usando informazioni specifiche del lettore di smart card.</span><span class="sxs-lookup"><span data-stu-id="82c34-124">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="82c34-125">Per altre informazioni, vedere la documentazione relativa al lettore.</span><span class="sxs-lookup"><span data-stu-id="82c34-125">For more information, see the documentation of your card reader.</span></span>
