---
title: "Procedura dettagliata: creazione di un'applicazione di crittografia"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 6e2d9b8bebdfd2ea5d5507cc73d444fa8bf785fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705834"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="b37dc-102">Procedura dettagliata: creazione di un'applicazione di crittografia</span><span class="sxs-lookup"><span data-stu-id="b37dc-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="b37dc-103">Questa procedura dettagliata illustra come crittografare e decrittografare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b37dc-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="b37dc-104">Gli esempi di codice sono progettati per un'applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b37dc-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="b37dc-105">Questa applicazione non illustra situazioni del mondo reale, come l'utilizzo di smart card.</span><span class="sxs-lookup"><span data-stu-id="b37dc-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="b37dc-106">Al contrario illustra gli aspetti fondamentali della crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="b37dc-107">Questa procedura dettagliata usa le linee guida seguenti per la crittografia:</span><span class="sxs-lookup"><span data-stu-id="b37dc-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
- <span data-ttu-id="b37dc-108">Usare la classe <xref:System.Security.Cryptography.RijndaelManaged>, un algoritmo simmetrico, per crittografare e decrittografare dati mediante le proprietà <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> e <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> generate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b37dc-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
- <span data-ttu-id="b37dc-109">Usare <xref:System.Security.Cryptography.RSACryptoServiceProvider>, un algoritmo generato automaticamente, per crittografare e decrittografare la chiave di dati crittografati da <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="b37dc-110">Gli algoritmi asimmetrici sono ideali per più piccole quantità di dati, come ad esempio una chiave.</span><span class="sxs-lookup"><span data-stu-id="b37dc-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b37dc-111">Se si vogliono proteggere dati sul computer anziché scambiare contenuto crittografato con altri utenti, è possibile usare le classi <xref:System.Security.Cryptography.ProtectedData> o <xref:System.Security.Cryptography.ProtectedMemory>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="b37dc-112">Nella seguente tabella sono riepilogate le attività crittografate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b37dc-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="b37dc-113">Attività</span><span class="sxs-lookup"><span data-stu-id="b37dc-113">Task</span></span>|<span data-ttu-id="b37dc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b37dc-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b37dc-115">Creazione di un'applicazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="b37dc-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="b37dc-116">Elenca i controlli necessari per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b37dc-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="b37dc-117">Dichiarazione di oggetti globali</span><span class="sxs-lookup"><span data-stu-id="b37dc-117">Declaring global objects</span></span>|<span data-ttu-id="b37dc-118">Dichiara le variabili del percorso stringa, <xref:System.Security.Cryptography.CspParameters> e <xref:System.Security.Cryptography.RSACryptoServiceProvider> per avere il contenuto globale della classe <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="b37dc-119">Creazione di una chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="b37dc-119">Creating an asymmetric key</span></span>|<span data-ttu-id="b37dc-120">Crea una coppia chiave-valore pubblica e privata asimmetrica e le assegna un nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b37dc-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="b37dc-121">Crittografia di un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-121">Encrypting a file</span></span>|<span data-ttu-id="b37dc-122">Visualizza una finestra di dialogo per selezionare un file per la crittografia e lo crittografa.</span><span class="sxs-lookup"><span data-stu-id="b37dc-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="b37dc-123">Decrittografia di un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-123">Decrypting a file</span></span>|<span data-ttu-id="b37dc-124">Visualizza una finestra di dialogo per selezionare un file crittografato per la decrittografia e lo decrittografa.</span><span class="sxs-lookup"><span data-stu-id="b37dc-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="b37dc-125">Recupero di una chiave privata</span><span class="sxs-lookup"><span data-stu-id="b37dc-125">Getting a private key</span></span>|<span data-ttu-id="b37dc-126">Ottiene una coppia di chiavi completa usando il nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b37dc-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="b37dc-127">Esportazione di una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-127">Exporting a public key</span></span>|<span data-ttu-id="b37dc-128">Salva la chiave in un file XML con solo parametri pubblici.</span><span class="sxs-lookup"><span data-stu-id="b37dc-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="b37dc-129">Importazione di una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-129">Importing a public key</span></span>|<span data-ttu-id="b37dc-130">Carica la chiave da un file XML in un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b37dc-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="b37dc-131">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b37dc-131">Testing the application</span></span>|<span data-ttu-id="b37dc-132">Elenca le procedure per il test di questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="b37dc-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="b37dc-133">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b37dc-133">Prerequisites</span></span>  
 <span data-ttu-id="b37dc-134">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b37dc-134">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="b37dc-135">Riferimenti agli spazi dei nomi <xref:System.IO> e <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="b37dc-136">Creazione di un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b37dc-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="b37dc-137">La maggior parte degli esempi di codice in questa procedura dettagliata sono progettati per essere gestori di eventi per i controlli pulsante.</span><span class="sxs-lookup"><span data-stu-id="b37dc-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="b37dc-138">Nella tabella seguente sono elencati i controlli necessari per l'applicazione di esempio e i relativi nomi richiesti per la corrispondenza con gli esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="b37dc-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="b37dc-139">Control</span><span class="sxs-lookup"><span data-stu-id="b37dc-139">Control</span></span>|<span data-ttu-id="b37dc-140">Name</span><span class="sxs-lookup"><span data-stu-id="b37dc-140">Name</span></span>|<span data-ttu-id="b37dc-141">Proprietà di testo (in base alle necessità)</span><span class="sxs-lookup"><span data-stu-id="b37dc-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="b37dc-142">Crittografa un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="b37dc-143">Decrittografa un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="b37dc-144">Crea chiavi</span><span class="sxs-lookup"><span data-stu-id="b37dc-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="b37dc-145">Esporta una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="b37dc-146">Importa una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="b37dc-147">Ottiene una chiave privata</span><span class="sxs-lookup"><span data-stu-id="b37dc-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`|<span data-ttu-id="b37dc-148">Chiave non impostata</span><span class="sxs-lookup"><span data-stu-id="b37dc-148">Key not set</span></span>|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="b37dc-149">Fare doppio clic sul pulsante nella finestra di progettazione di Visual Studio per creare i relativi gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="b37dc-149">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="b37dc-150">Dichiarazione di oggetti globali</span><span class="sxs-lookup"><span data-stu-id="b37dc-150">Declaring Global Objects</span></span>  
 <span data-ttu-id="b37dc-151">Aggiungere il seguente codice al costruttore del form:</span><span class="sxs-lookup"><span data-stu-id="b37dc-151">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="b37dc-152">Modificare le variabili di stringa per l'ambiente e le preferenze.</span><span class="sxs-lookup"><span data-stu-id="b37dc-152">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="b37dc-153">Creazione di una chiave asimmetrica</span><span class="sxs-lookup"><span data-stu-id="b37dc-153">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="b37dc-154">Questa attività crea una chiave asimmetrica che crittografa e decrittografa la chiave <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-154">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="b37dc-155">Questa chiave era usata per crittografare il contenuto e visualizza il nome del contenitore di chiavi nel controllo etichetta.</span><span class="sxs-lookup"><span data-stu-id="b37dc-155">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="b37dc-156">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Create Keys` (`buttonCreateAsmKeys_Click`).</span><span class="sxs-lookup"><span data-stu-id="b37dc-156">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="b37dc-157">Crittografia di un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-157">Encrypting a File</span></span>  
 <span data-ttu-id="b37dc-158">Questa attività include due metodi: il metodo del gestore eventi per il pulsante `Encrypt File` (`buttonEncryptFile_Click`) e il metodo `EncryptFile`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-158">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="b37dc-159">Il primo metodo visualizza una finestra di dialogo per la selezione di un file e passa il nome file al secondo metodo, che esegue la crittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-159">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="b37dc-160">Il contenuto, la chiave e il vettore di inizializzazione (IV) crittografati vengono tutti salvati in un <xref:System.IO.FileStream>, a cui si fa riferimento come pacchetto di crittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-160">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="b37dc-161">Il metodo `EncryptFile` esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b37dc-161">The `EncryptFile` method does the following:</span></span>  
  
1. <span data-ttu-id="b37dc-162">Crea un algoritmo simmetrico <xref:System.Security.Cryptography.RijndaelManaged> per crittografare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b37dc-162">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2. <span data-ttu-id="b37dc-163">Crea un oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> per crittografare la chiave <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-163">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3. <span data-ttu-id="b37dc-164">Usa un oggetto <xref:System.Security.Cryptography.CryptoStream> per leggere e crittografare <xref:System.IO.FileStream> del file di origine, in blocchi di byte, in un oggetto <xref:System.IO.FileStream> di destinazione per il file crittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-164">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4. <span data-ttu-id="b37dc-165">Determina le lunghezze della chiave e del vettore di inizializzazione (IV) crittografati e crea matrici di byte dei valori delle relative lunghezze.</span><span class="sxs-lookup"><span data-stu-id="b37dc-165">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5. <span data-ttu-id="b37dc-166">Scrive la chiave, il vettore di inizializzazione (IV) e i valori delle relative lunghezze nel pacchetto di crittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-166">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="b37dc-167">Il pacchetto di crittografia usa il seguente formato:</span><span class="sxs-lookup"><span data-stu-id="b37dc-167">The encryption package uses the following format:</span></span>  
  
- <span data-ttu-id="b37dc-168">Lunghezza chiave, byte 0 - 3</span><span class="sxs-lookup"><span data-stu-id="b37dc-168">Key length, bytes 0 - 3</span></span>  
  
- <span data-ttu-id="b37dc-169">Lunghezza vettore di inizializzazione, byte 4 - 7</span><span class="sxs-lookup"><span data-stu-id="b37dc-169">IV length, bytes 4 - 7</span></span>  
  
- <span data-ttu-id="b37dc-170">Chiave crittografata</span><span class="sxs-lookup"><span data-stu-id="b37dc-170">Encrypted key</span></span>  
  
- <span data-ttu-id="b37dc-171">Vettore di inizializzazione (IV)</span><span class="sxs-lookup"><span data-stu-id="b37dc-171">IV</span></span>  
  
- <span data-ttu-id="b37dc-172">Testo crittografato</span><span class="sxs-lookup"><span data-stu-id="b37dc-172">Cipher text</span></span>  
  
 <span data-ttu-id="b37dc-173">È possibile usare le lunghezze della chiave e del vettore di inizializzazione (IV) per determinare i punti iniziali e lunghezze di tutte le parti del pacchetto di crittografia, che quindi può essere usato per decrittografare il file.</span><span class="sxs-lookup"><span data-stu-id="b37dc-173">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="b37dc-174">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Encrypt File` (`buttonEncryptFile_Click`).</span><span class="sxs-lookup"><span data-stu-id="b37dc-174">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="b37dc-175">Aggiungere il metodo `EncryptFile` seguente al form.</span><span class="sxs-lookup"><span data-stu-id="b37dc-175">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="b37dc-176">Decrittografia di un file</span><span class="sxs-lookup"><span data-stu-id="b37dc-176">Decrypting a File</span></span>  
 <span data-ttu-id="b37dc-177">Per questa attività vengono usati due metodi: il metodo gestore eventi per il pulsante `Decrypt File` (`buttonDecryptFile_Click`) e il metodo `DecryptFile`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-177">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="b37dc-178">Il primo metodo visualizza una finestra di dialogo per la selezione di un file e passa il nome file al secondo metodo, che esegue la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-178">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="b37dc-179">Il metodo `Decrypt` esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b37dc-179">The `Decrypt` method does the following:</span></span>  
  
1. <span data-ttu-id="b37dc-180">Crea un algoritmo simmetrico <xref:System.Security.Cryptography.RijndaelManaged> per decrittografare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b37dc-180">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2. <span data-ttu-id="b37dc-181">Legge i primi otto byte del pacchetto crittografato <xref:System.IO.FileStream> in matrici di byte per ottenere le lunghezze della chiave e del vettore di inizializzazione crittografati.</span><span class="sxs-lookup"><span data-stu-id="b37dc-181">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3. <span data-ttu-id="b37dc-182">Estrae la chiave e il vettore di inizializzazione dal pacchetto di crittografia in matrici di byte.</span><span class="sxs-lookup"><span data-stu-id="b37dc-182">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4. <span data-ttu-id="b37dc-183">Crea un oggetto <xref:System.Security.Cryptography.RSACryptoServiceProvider> per decrittografare la chiave <xref:System.Security.Cryptography.RijndaelManaged>.</span><span class="sxs-lookup"><span data-stu-id="b37dc-183">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5. <span data-ttu-id="b37dc-184">Usa un oggetto <xref:System.Security.Cryptography.CryptoStream> per leggere e decrittografare la sezione del testo crittografato del pacchetto di crittografia <xref:System.IO.FileStream>, in blocchi di byte, nell'oggetto <xref:System.IO.FileStream> per il file decrittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-184">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="b37dc-185">Quando questa operazione è terminata, la decrittografia è completata.</span><span class="sxs-lookup"><span data-stu-id="b37dc-185">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="b37dc-186">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Decrypt File`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-186">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="b37dc-187">Aggiungere il metodo `DecryptFile` seguente al form.</span><span class="sxs-lookup"><span data-stu-id="b37dc-187">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="b37dc-188">Esportazione di una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-188">Exporting a Public Key</span></span>  
 <span data-ttu-id="b37dc-189">Questa attività salva la chiave creata dal pulsante `Create Keys` in un file.</span><span class="sxs-lookup"><span data-stu-id="b37dc-189">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="b37dc-190">Esporta solo i parametri pubblici.</span><span class="sxs-lookup"><span data-stu-id="b37dc-190">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="b37dc-191">Questa attività simula lo scenario in cui Alice fornisce a Bob la sua chiave pubblica affinché egli possa crittografare i file per Alice.</span><span class="sxs-lookup"><span data-stu-id="b37dc-191">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="b37dc-192">Bob e altri utenti che dispongono di quella chiave pubblica non saranno in grado di decrittografarli poiché non possiedono la coppia di chiavi completa con i parametri privati.</span><span class="sxs-lookup"><span data-stu-id="b37dc-192">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="b37dc-193">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Export Public Key` (`buttonExportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="b37dc-193">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="b37dc-194">Importazione di una chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-194">Importing a Public Key</span></span>  
 <span data-ttu-id="b37dc-195">Questa attività carica la chiave con solo parametri pubblici, come creati dal pulsante `Export Public Key` e la imposta come nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b37dc-195">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="b37dc-196">Questa attività simula lo scenario di Bob che carica la chiave di Alice con solo parametri pubblici in modo che possa crittografare file per conto di Alice.</span><span class="sxs-lookup"><span data-stu-id="b37dc-196">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="b37dc-197">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Import Public Key` (`buttonImportPublicKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="b37dc-197">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="b37dc-198">Recupero di una chiave privata</span><span class="sxs-lookup"><span data-stu-id="b37dc-198">Getting a Private Key</span></span>  
 <span data-ttu-id="b37dc-199">Questa attività imposta il nome del contenitore di chiavi sul nome della chiave creata mediante il pulsante `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-199">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="b37dc-200">Il contenitore di chiavi conterrà la coppia di chiavi completa con parametri privati.</span><span class="sxs-lookup"><span data-stu-id="b37dc-200">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="b37dc-201">Questa attività simula lo scenario di Alice che usa la propria chiave privata per decrittografare file crittografati da Bob.</span><span class="sxs-lookup"><span data-stu-id="b37dc-201">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="b37dc-202">Aggiungere il codice seguente come gestore eventi `Click` per il pulsante `Get Private Key` (`buttonGetPrivateKey_Click`).</span><span class="sxs-lookup"><span data-stu-id="b37dc-202">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="b37dc-203">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b37dc-203">Testing the Application</span></span>  
 <span data-ttu-id="b37dc-204">Dopo aver compilato l'applicazione, eseguire gli scenari di test seguenti.</span><span class="sxs-lookup"><span data-stu-id="b37dc-204">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="b37dc-205">Per creare chiavi, crittografare e decrittografare</span><span class="sxs-lookup"><span data-stu-id="b37dc-205">To create keys, encrypt, and decrypt</span></span>  
  
1. <span data-ttu-id="b37dc-206">Fare clic sul pulsante `Create Keys`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-206">Click the `Create Keys` button.</span></span> <span data-ttu-id="b37dc-207">L'etichetta visualizza il nome della chiave e mostra che è una coppia di chiavi completa.</span><span class="sxs-lookup"><span data-stu-id="b37dc-207">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2. <span data-ttu-id="b37dc-208">Fare clic sul pulsante `Export Public Key`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-208">Click the `Export Public Key` button.</span></span> <span data-ttu-id="b37dc-209">Si noti che l'esportazione dei parametri della chiave pubblica non modifica la chiave corrente.</span><span class="sxs-lookup"><span data-stu-id="b37dc-209">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3. <span data-ttu-id="b37dc-210">Fare clic sul pulsante `Encrypt File` e selezionare un file.</span><span class="sxs-lookup"><span data-stu-id="b37dc-210">Click the `Encrypt File` button and select a file.</span></span>  
  
4. <span data-ttu-id="b37dc-211">Fare clic sul pulsante `Decrypt File` e selezionare il file appena crittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-211">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5. <span data-ttu-id="b37dc-212">Esaminare il file appena decrittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-212">Examine the file just decrypted.</span></span>  
  
6. <span data-ttu-id="b37dc-213">Chiudere l'applicazione e riavviarla per testare il recupero dei contenitori di chiavi persistenti nello scenario successivo.</span><span class="sxs-lookup"><span data-stu-id="b37dc-213">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="b37dc-214">Per crittografare mediante la chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="b37dc-214">To encrypt using the public key</span></span>  
  
1. <span data-ttu-id="b37dc-215">Fare clic sul pulsante `Import Public Key`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-215">Click the `Import Public Key` button.</span></span> <span data-ttu-id="b37dc-216">L'etichetta visualizza il nome della chiave e mostra che è solo pubblica.</span><span class="sxs-lookup"><span data-stu-id="b37dc-216">The label displays the key name and shows that it is public only.</span></span>  
  
2. <span data-ttu-id="b37dc-217">Fare clic sul pulsante `Encrypt File` e selezionare un file.</span><span class="sxs-lookup"><span data-stu-id="b37dc-217">Click the `Encrypt File` button and select a file.</span></span>  
  
3. <span data-ttu-id="b37dc-218">Fare clic sul pulsante `Decrypt File` e selezionare il file appena crittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-218">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="b37dc-219">Questa operazione avrà esito negativo perché si deve avere a disposizione la chiave privata per decrittografare.</span><span class="sxs-lookup"><span data-stu-id="b37dc-219">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="b37dc-220">Questo scenario illustra una situazione in cui si possiede solo la chiave pubblica per crittografare un file per un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="b37dc-220">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="b37dc-221">In genere quella persona potrebbe mettere a disposizione solo la chiave pubblica e mantenere quella privata per la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="b37dc-221">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="b37dc-222">Per decrittografare mediante la chiave privata</span><span class="sxs-lookup"><span data-stu-id="b37dc-222">To decrypt using the private key</span></span>  
  
1. <span data-ttu-id="b37dc-223">Fare clic sul pulsante `Get Private Key`.</span><span class="sxs-lookup"><span data-stu-id="b37dc-223">Click the `Get Private Key` button.</span></span> <span data-ttu-id="b37dc-224">L'etichetta visualizza il nome della chiave e mostra se è la coppia di chiavi completa.</span><span class="sxs-lookup"><span data-stu-id="b37dc-224">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2. <span data-ttu-id="b37dc-225">Fare clic sul pulsante `Decrypt File` e selezionare il file appena crittografato.</span><span class="sxs-lookup"><span data-stu-id="b37dc-225">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="b37dc-226">Questa operazione avrà esito positivo perché si possiede la coppia di chiavi completa per decrittografare.</span><span class="sxs-lookup"><span data-stu-id="b37dc-226">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b37dc-227">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b37dc-227">See also</span></span>

- [<span data-ttu-id="b37dc-228">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b37dc-228">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
