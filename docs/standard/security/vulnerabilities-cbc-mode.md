---
title: Vulnerabilità di decrittografia CBC
description: Scopri come rilevare e ridurre le vulnerabilità di temporizzazione con la decrittografia simmetrica in modalità CBC (Cipher-Block-Chaining) usando la spaziatura interna.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186088"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="47609-103">Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento</span><span class="sxs-lookup"><span data-stu-id="47609-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="47609-104">Microsoft ritiene che non sia più sicuro decrittografare i dati crittografati con la modalità Cipher-Block-Chaining (CBC) di crittografia simmetrica quando è stata applicata una spaziatura interna verificabile senza prima garantire l'integrità del testo crittografato, ad eccezione di Circostanze.</span><span class="sxs-lookup"><span data-stu-id="47609-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="47609-105">Questo giudizio si basa su ricerche crittografiche attualmente note.</span><span class="sxs-lookup"><span data-stu-id="47609-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="47609-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="47609-106">Introduction</span></span>

<span data-ttu-id="47609-107">Un attacco oracolo imbottitura è un tipo di attacco contro i dati crittografati che consente all'utente malintenzionato di decrittografare il contenuto dei dati, senza conoscere la chiave.</span><span class="sxs-lookup"><span data-stu-id="47609-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="47609-108">Un oracolo si riferisce a un "racconto" che fornisce a un utente malintenzionato informazioni sul fatto che l'azione che sta eseguendo sia corretta o meno.</span><span class="sxs-lookup"><span data-stu-id="47609-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="47609-109">Immagina di giocare a un gioco da tavolo o a carte con un bambino.</span><span class="sxs-lookup"><span data-stu-id="47609-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="47609-110">Quando il loro viso si illumina con un grande sorriso perché pensano di fare una buona mossa, è un oracolo.</span><span class="sxs-lookup"><span data-stu-id="47609-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="47609-111">Tu, come avversario, puoi usare questo oracolo per pianificare la tua prossima mossa in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="47609-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="47609-112">Padding è un termine crittografico specifico.</span><span class="sxs-lookup"><span data-stu-id="47609-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="47609-113">Alcuni cifrari, che sono gli algoritmi utilizzati per crittografare i dati, funzionano su blocchi di dati in cui ogni blocco è di dimensioni fisse.</span><span class="sxs-lookup"><span data-stu-id="47609-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="47609-114">Se i dati che si desidera crittografare non sono la dimensione corretta per riempire i blocchi, i dati vengono riempiti fino a quando non lo fa.</span><span class="sxs-lookup"><span data-stu-id="47609-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="47609-115">Molte forme di riempimento richiedono che la spaziatura interna sia sempre presente, anche se l'input originale era della dimensione corretta.</span><span class="sxs-lookup"><span data-stu-id="47609-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="47609-116">Ciò consente di rimuovere sempre l'imbottitura in modo sicuro al momento della decrittografia.</span><span class="sxs-lookup"><span data-stu-id="47609-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="47609-117">Mettendo insieme le due cose, un'implementazione software con un oracolo imbottitura rivela se i dati decrittografati hanno una spaziatura interna valida.</span><span class="sxs-lookup"><span data-stu-id="47609-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="47609-118">L'oracolo potrebbe essere qualcosa di semplice come la restituzione di un valore che dice "padding non valido" o qualcosa di più complicato come prendere un tempo misurabilmente diverso per elaborare un blocco valido al contrario di un blocco non valido.</span><span class="sxs-lookup"><span data-stu-id="47609-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="47609-119">Le crittografie basate su blocchi hanno un'altra proprietà, denominata modalità, che determina la relazione dei dati nel primo blocco con i dati nel secondo blocco e così via.</span><span class="sxs-lookup"><span data-stu-id="47609-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="47609-120">Una delle modalità più comunemente utilizzate è CBC.</span><span class="sxs-lookup"><span data-stu-id="47609-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="47609-121">CBC introduce un blocco casuale iniziale, noto come vettore di inizializzazione (IV), e combina il blocco precedente con il risultato della crittografia statica per rendere tale che la crittografia dello stesso messaggio con la stessa chiave non produca sempre lo stesso output crittografato.</span><span class="sxs-lookup"><span data-stu-id="47609-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="47609-122">Un utente malintenzionato può utilizzare un oracolo di spaziatura interna, in combinazione con il modo in cui sono strutturati i dati CBC, per inviare messaggi leggermente modificati al codice che espone l'oracolo e continuare a inviare dati fino a quando l'oracolo non indica che i dati sono corretti.</span><span class="sxs-lookup"><span data-stu-id="47609-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="47609-123">Da questa risposta, l'utente malintenzionato può decrittografare il byte del messaggio per byte.</span><span class="sxs-lookup"><span data-stu-id="47609-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="47609-124">Le reti di computer moderne sono di qualità così elevata che un utente malintenzionato può rilevare differenze molto piccole (meno di 0,1 ms) nel tempo di esecuzione sui sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="47609-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="47609-125">Le applicazioni che assumono che una decrittografia di successo può verificarsi solo quando i dati non è stato manomesso potrebbe essere vulnerabile agli attacchi da strumenti che sono progettati per osservare le differenze nella decrittografia riuscita e non riuscita.</span><span class="sxs-lookup"><span data-stu-id="47609-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="47609-126">Anche se questa differenza di temporizzazione può essere più significativa in alcuni linguaggi o librerie rispetto ad altri, si ritiene ora che questa sia una minaccia pratica per tutti i linguaggi e le librerie quando viene presa in considerazione la risposta dell'applicazione all'errore.</span><span class="sxs-lookup"><span data-stu-id="47609-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="47609-127">Questo attacco si basa sulla possibilità di modificare i dati crittografati e testare il risultato con l'oracolo.</span><span class="sxs-lookup"><span data-stu-id="47609-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="47609-128">L'unico modo per mitigare completamente l'attacco è quello di rilevare le modifiche ai dati crittografati e rifiutare di eseguire qualsiasi azione su di esso.</span><span class="sxs-lookup"><span data-stu-id="47609-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="47609-129">Il modo standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima che vengano eseguite le operazioni.</span><span class="sxs-lookup"><span data-stu-id="47609-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="47609-130">La firma deve essere verificabile, non può essere creata dall'utente malintenzionato, altrimenti modificherebbe i dati crittografati, quindi calcola una nuova firma in base ai dati modificati.</span><span class="sxs-lookup"><span data-stu-id="47609-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="47609-131">Un tipo comune di firma appropriata è noto come codice HMAC (Keyed-Hash Message Authentication Code).</span><span class="sxs-lookup"><span data-stu-id="47609-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="47609-132">Un HMAC differisce da un checksum in quanto richiede una chiave segreta, nota solo alla persona che produce l'HMAC e alla persona che la convalida.</span><span class="sxs-lookup"><span data-stu-id="47609-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="47609-133">Senza il possesso della chiave, non è possibile produrre un HMAC corretto.</span><span class="sxs-lookup"><span data-stu-id="47609-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="47609-134">Quando si ricevono i dati, è necessario prendere i dati crittografati, calcolare in modo indipendente l'HMAC utilizzando la chiave segreta che tu e il mittente condividete, quindi confrontare l'HMAC inviato con quello calcolato.</span><span class="sxs-lookup"><span data-stu-id="47609-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="47609-135">Questo confronto deve essere un tempo costante, altrimenti hai aggiunto un altro oracolo rilevabile, consentendo un diverso tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="47609-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="47609-136">In sintesi, per utilizzare i cifrari a blocchi CBC imbottiti in modo sicuro, è necessario combinarli con un HMAC (o un altro controllo di integrità dei dati) convalidato utilizzando un confronto temporale costante prima di tentare di decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="47609-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="47609-137">Poiché tutti i messaggi alterati richiedono la stessa quantità di tempo per produrre una risposta, l'attacco viene impedito.</span><span class="sxs-lookup"><span data-stu-id="47609-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="47609-138">Chi è vulnerabile</span><span class="sxs-lookup"><span data-stu-id="47609-138">Who is vulnerable</span></span>

<span data-ttu-id="47609-139">Questa vulnerabilità si applica sia alle applicazioni gestite che native che eseguono la propria crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="47609-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="47609-140">Ciò include, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47609-140">This includes, for example:</span></span>

- <span data-ttu-id="47609-141">Applicazione che crittografa un cookie per la decrittografia successiva sul server.</span><span class="sxs-lookup"><span data-stu-id="47609-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="47609-142">Applicazione di database che consente agli utenti di inserire dati in una tabella le cui colonne vengono successivamente decrittografate.</span><span class="sxs-lookup"><span data-stu-id="47609-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="47609-143">Un'applicazione di trasferimento dati che si basa sulla crittografia utilizzando una chiave condivisa per proteggere i dati in transito.</span><span class="sxs-lookup"><span data-stu-id="47609-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="47609-144">Un'applicazione che crittografa e decrittografa i messaggi "all'interno" del tunnel TLS.</span><span class="sxs-lookup"><span data-stu-id="47609-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="47609-145">Tieni presente che l'utilizzo di TLS da solo potrebbe non proteggere l'utente in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="47609-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="47609-146">Un'applicazione vulnerabile:</span><span class="sxs-lookup"><span data-stu-id="47609-146">A vulnerable application:</span></span>

- <span data-ttu-id="47609-147">Decrittografa i dati utilizzando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio PKCS-7 o ANSI X.923.</span><span class="sxs-lookup"><span data-stu-id="47609-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="47609-148">Esegue la decrittografia senza aver eseguito un controllo di integrità dei dati (tramite un MAC o una firma digitale asimmetrica).</span><span class="sxs-lookup"><span data-stu-id="47609-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="47609-149">Questo vale anche per le applicazioni basate sulle astrazioni sopra queste primitive, ad esempio la struttura EnvelopedData della sintassi dei messaggi di crittografia (PKCS/7/CMS).</span><span class="sxs-lookup"><span data-stu-id="47609-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="47609-150">Aree di interesse correlate</span><span class="sxs-lookup"><span data-stu-id="47609-150">Related areas of concern</span></span>

<span data-ttu-id="47609-151">La ricerca ha portato Microsoft a essere ulteriormente preoccupato per i messaggi CBC che sono imbottiti con spaziatura interna equivalente ISO 10126 quando il messaggio ha una struttura di piè di pagina nota o prevedibile.</span><span class="sxs-lookup"><span data-stu-id="47609-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="47609-152">Ad esempio, il contenuto preparato in base alle regole del W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="47609-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="47609-153">Mentre le linee guida W3C per firmare il messaggio quindi crittografare è stato considerato appropriato al momento, Microsoft ora consiglia di eseguire sempre crittografia-poi-firma.</span><span class="sxs-lookup"><span data-stu-id="47609-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="47609-154">Gli sviluppatori di applicazioni devono sempre tenere presente l'applicabilità di una chiave di firma asimmetrica, in quanto non esiste alcuna relazione di trust intrinseca tra una chiave asimmetrica e un messaggio arbitrario.</span><span class="sxs-lookup"><span data-stu-id="47609-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="47609-155">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47609-155">Details</span></span>

<span data-ttu-id="47609-156">Storicamente, c'è stato consenso sul fatto che sia importante crittografare e autenticare i dati importanti, utilizzando mezzi come le firme HMAC o RSA.</span><span class="sxs-lookup"><span data-stu-id="47609-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="47609-157">Tuttavia, sono state fornite indicazioni meno chiare su come sequenziare le operazioni di crittografia e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="47609-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="47609-158">A causa della vulnerabilità descritta in questo articolo, la guida di Microsoft è ora di utilizzare sempre il paradigma "crittografa-allora-firma".</span><span class="sxs-lookup"><span data-stu-id="47609-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="47609-159">Ovvero, prima crittografare i dati utilizzando una chiave simmetrica, quindi calcolare una firma MAC o asimmetrica sul testo crittografato (dati crittografati).</span><span class="sxs-lookup"><span data-stu-id="47609-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="47609-160">Quando si decrittografano i dati, eseguire l'inverso.</span><span class="sxs-lookup"><span data-stu-id="47609-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="47609-161">In primo luogo, confermare il MAC o la firma del testo cifrato, quindi decrittografarlo.</span><span class="sxs-lookup"><span data-stu-id="47609-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="47609-162">Una classe di vulnerabilità note come "attacchi oracolo imbottitura" sono stati conosciuti per esistere per oltre 10 anni.</span><span class="sxs-lookup"><span data-stu-id="47609-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="47609-163">Queste vulnerabilità consentono a un utente malintenzionato di decrittografare i dati crittografati da algoritmi a blocchi simmetrici, ad esempio AES e 3DES, utilizzando non più di 4096 tentativi per blocco di dati.</span><span class="sxs-lookup"><span data-stu-id="47609-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="47609-164">Queste vulnerabilità fanno uso del fatto che i cifrari a blocchi sono più frequentemente utilizzati con i dati di riempimento verificabili alla fine.</span><span class="sxs-lookup"><span data-stu-id="47609-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="47609-165">Si è scoperto che se un utente malintenzionato può manomettere il testo crittografato e scoprire se la manomissione ha causato un errore nel formato della spaziatura interna alla fine, l'utente malintenzionato può decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="47609-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="47609-166">Inizialmente, gli attacchi pratici erano basati su servizi che restituivano codici di errore diversi a seconda che la spaziatura interna fosse valida, ad esempio la vulnerabilità ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span><span class="sxs-lookup"><span data-stu-id="47609-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="47609-167">Tuttavia, Microsoft ritiene ora che sia pratico condurre attacchi simili utilizzando solo le differenze di tempo tra l'elaborazione di riempimento valido e non valido.</span><span class="sxs-lookup"><span data-stu-id="47609-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="47609-168">A condizione che lo schema di crittografia impieghi una firma e che la verifica della firma venga eseguita con un runtime fisso per una determinata lunghezza di dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza emettere alcuna informazione a un utente malintenzionato tramite un [canale laterale.](https://en.wikipedia.org/wiki/Side-channel_attack)</span><span class="sxs-lookup"><span data-stu-id="47609-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="47609-169">Poiché il controllo di integrità rifiuta tutti i messaggi manomessi, la minaccia dell'oracolo della spaziatura interna viene attenuata.</span><span class="sxs-lookup"><span data-stu-id="47609-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="47609-170">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="47609-170">Guidance</span></span>

<span data-ttu-id="47609-171">In primo luogo, Microsoft consiglia di trasmettere tutti i dati con necessità di riservatezza tramite Transport Layer Security (TLS), il successore di Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="47609-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="47609-172">Successivamente, analizzare l'applicazione per:Next, analyze your application to:</span><span class="sxs-lookup"><span data-stu-id="47609-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="47609-173">Comprendere con precisione quale crittografia si sta eseguendo e quale crittografia viene fornita dalle piattaforme e API in uso.</span><span class="sxs-lookup"><span data-stu-id="47609-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="47609-174">Assicurarsi che ogni utilizzo a ogni livello di un algoritmo di crittografia a [blocchi simmetrico,](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)ad esempio AES e 3DES, in modalità CBC incorpori l'utilizzo di un controllo di integrità dei dati con chiave segreta (una firma asimmetrica, un HMAC o per modificare la modalità di crittografia in una modalità di [crittografia autenticata](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE), ad esempio GCM o CCM.</span><span class="sxs-lookup"><span data-stu-id="47609-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="47609-175">Sulla base della ricerca corrente, è generalmente creduto che quando i passaggi di autenticazione e crittografia vengono eseguiti in modo indipendente per le modalità di crittografia non AE, l'autenticazione del testo crittografato (crittografia-poi-firma) è la migliore opzione generale.</span><span class="sxs-lookup"><span data-stu-id="47609-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="47609-176">Tuttavia, non c'è nessuna risposta corretta per tutti e questa generalizzazione non è buona come la consulenza diretta di un crittografo professionista.</span><span class="sxs-lookup"><span data-stu-id="47609-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="47609-177">Le applicazioni che non sono in grado di modificare il formato di messaggistica ma eseguono la decrittografia CBC non autenticata sono incoraggiate a provare a incorporare attenuazioni come:</span><span class="sxs-lookup"><span data-stu-id="47609-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="47609-178">Decrittografare senza consentire al decryptor di verificare o rimuovere la spaziatura interna:</span><span class="sxs-lookup"><span data-stu-id="47609-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="47609-179">Qualsiasi riempimento che è stato applicato deve ancora essere rimosso o ignorato, si sta spostando il carico nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47609-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="47609-180">Il vantaggio è che la verifica e la rimozione della spaziatura interna possono essere incorporate in altre logiche di verifica dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47609-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="47609-181">Se la verifica dell'imbottitura e la verifica dei dati possono essere eseguite in tempi costanti, la minaccia viene ridotta.</span><span class="sxs-lookup"><span data-stu-id="47609-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="47609-182">Poiché l'interpretazione della spaziatura interna modifica la lunghezza del messaggio percepito, potrebbero essere ancora presenti informazioni di temporizzazione generate da questo approccio.</span><span class="sxs-lookup"><span data-stu-id="47609-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="47609-183">Modificare la modalità di decrittografia padding in ISO10126:</span><span class="sxs-lookup"><span data-stu-id="47609-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="47609-184">La spaziatura interna di decrittografia ISO10126 è compatibile sia con la spaziatura interna di crittografia PKCS7 che con la spaziatura interna di crittografia ANSIX923.</span><span class="sxs-lookup"><span data-stu-id="47609-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="47609-185">La modifica della modalità riduce la conoscenza dell'oracolo di riempimento a 1 byte anziché l'intero blocco.</span><span class="sxs-lookup"><span data-stu-id="47609-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="47609-186">Tuttavia, se il contenuto ha un piè di pagina noto, ad esempio un elemento XML di chiusura, gli attacchi correlati possono continuare ad attaccare il resto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="47609-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="47609-187">In questo modo non viene inoltre impedito il ripristino in testo normale in situazioni in cui l'utente malintenzionato può coemettere lo stesso testo in chiaro da crittografare più volte con un offset del messaggio diverso.</span><span class="sxs-lookup"><span data-stu-id="47609-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="47609-188">Gate la valutazione di una chiamata di decrittazione per smorzare il segnale di temporizzazione:</span><span class="sxs-lookup"><span data-stu-id="47609-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="47609-189">Il calcolo del tempo di conservazione deve avere un valore minimo superiore alla quantità massima di tempo necessaria per l'operazione di decrittografia per qualsiasi segmento di dati che contiene spaziatura interna.</span><span class="sxs-lookup"><span data-stu-id="47609-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="47609-190">I calcoli temporali devono essere eseguiti in base alle indicazioni fornite <xref:System.Environment.TickCount?displayProperty=nameWithType> in Acquisizione di timestamp ad alta [risoluzione,](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)non utilizzando (soggetto a rollover/overflow) o sottraendo due timestamp di sistema (soggetto a errori di regolazione NTP).</span><span class="sxs-lookup"><span data-stu-id="47609-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="47609-191">I calcoli temporali devono includere l'operazione di decrittografia, incluse tutte le potenziali eccezioni nelle applicazioni gestite o in C, non solo riempite alla fine.</span><span class="sxs-lookup"><span data-stu-id="47609-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="47609-192">Se l'esito positivo o negativo è stato determinato ancora, il gate di temporizzazione deve restituire l'errore alla scadenza.</span><span class="sxs-lookup"><span data-stu-id="47609-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="47609-193">I servizi che eseguono la decrittografia non autenticata devono disporre di un monitoraggio per rilevare che è arrivata una marea di messaggi "non validi".</span><span class="sxs-lookup"><span data-stu-id="47609-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="47609-194">Tenete a mente che questo segnale trasporta sia falsi positivi (dati legittimamente corrotti) e falsi negativi (diffondendo l'attacco in un tempo sufficientemente lungo per eludere il rilevamento).</span><span class="sxs-lookup"><span data-stu-id="47609-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="47609-195">Ricerca di codice vulnerabile - applicazioni nativeFinding vulnerable code - native applications</span><span class="sxs-lookup"><span data-stu-id="47609-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="47609-196">Per i programmi creati in base alla libreria CNG (Windows Cryptography: Next Generation):</span><span class="sxs-lookup"><span data-stu-id="47609-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="47609-197">La chiamata di decrittografia è a [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specificando il `BCRYPT_BLOCK_PADDING` flag.</span><span class="sxs-lookup"><span data-stu-id="47609-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="47609-198">L'handle di chiave è stato inizializzato [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) chiamando `BCRYPT_CHAIN_MODE_CBC` [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con BCRYPT_CHAINING_MODE impostato su .</span><span class="sxs-lookup"><span data-stu-id="47609-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="47609-199">Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, il `BCRYPT_CHAINING_MODE`codice interessato potrebbe non avere assegnato alcun valore per .</span><span class="sxs-lookup"><span data-stu-id="47609-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="47609-200">Per i programmi creati in base alla precedente API di crittografia di Windows:</span><span class="sxs-lookup"><span data-stu-id="47609-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="47609-201">La chiamata di decrittografia è `Final=TRUE`a [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con .</span><span class="sxs-lookup"><span data-stu-id="47609-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="47609-202">L'handle di chiave è stato inizializzato [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) chiamando `CRYPT_MODE_CBC` [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con KP_MODE impostato su .</span><span class="sxs-lookup"><span data-stu-id="47609-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="47609-203">Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, il `KP_MODE`codice interessato potrebbe non avere assegnato alcun valore per .</span><span class="sxs-lookup"><span data-stu-id="47609-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="47609-204">Ricerca di codice vulnerabile - applicazioni gestiteFinding vulnerable code - managed applications</span><span class="sxs-lookup"><span data-stu-id="47609-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="47609-205">La chiamata di decrittografia <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> è <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>ai metodi o su .</span><span class="sxs-lookup"><span data-stu-id="47609-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="47609-206">Sono inclusi i seguenti tipi derivati all'interno di .NET, ma possono anche includere tipi di terze parti:</span><span class="sxs-lookup"><span data-stu-id="47609-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <span data-ttu-id="47609-207">La <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà è <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>stata <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>impostata su , , o .</span><span class="sxs-lookup"><span data-stu-id="47609-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="47609-208">Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> il codice interessato potrebbe non aver mai assegnato la proprietà.</span><span class="sxs-lookup"><span data-stu-id="47609-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="47609-209">La <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà è stata impostata su<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="47609-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="47609-210">Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> il codice interessato potrebbe non aver mai assegnato la proprietà.</span><span class="sxs-lookup"><span data-stu-id="47609-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="47609-211">Ricerca di codice vulnerabile - sintassi dei messaggi crittograficiFinding vulnerable code - cryptographic message syntax</span><span class="sxs-lookup"><span data-stu-id="47609-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="47609-212">Un messaggio CMS EnvelopedData non autenticato il cui contenuto crittografato utilizza la modalità CBC di AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) è vulnerabili, così come i messaggi che utilizzano qualsiasi altro algoritmo di crittografia a blocchi in modalità CBC.</span><span class="sxs-lookup"><span data-stu-id="47609-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="47609-213">Sebbene le crittografie di flusso non siano soggette a questa particolare vulnerabilità, Microsoft consiglia di autenticare sempre i dati durante l'ispezione del valore ContentEncryptionAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="47609-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="47609-214">Per le applicazioni gestite, un BLOB CMS EnvelopedData <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>può essere rilevato come qualsiasi valore passato a .</span><span class="sxs-lookup"><span data-stu-id="47609-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="47609-215">Per le applicazioni native, un BLOB CMS EnvelopedData può essere rilevato come qualsiasi valore `CMSG_ENVELOPED` fornito a un handle CMS `CMSG_CTRL_DECRYPT` tramite [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) il cui [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) risultante è e/o l'handle CMS viene successivamente inviato un'istruzione tramite [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span><span class="sxs-lookup"><span data-stu-id="47609-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="47609-216">Esempio di codice vulnerabile - gestitoVulnerable code example - managed</span><span class="sxs-lookup"><span data-stu-id="47609-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="47609-217">Questo metodo legge un cookie e lo decrittografa e non è visibile alcun controllo dell'integrità dei dati.</span><span class="sxs-lookup"><span data-stu-id="47609-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="47609-218">Pertanto, il contenuto di un cookie letto da questo metodo può essere attaccato dall'utente che lo ha ricevuto o da qualsiasi utente malintenzionato che ha ottenuto il valore del cookie crittografato.</span><span class="sxs-lookup"><span data-stu-id="47609-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="47609-219">Codice di esempio che segue le procedure consigliate : gestito</span><span class="sxs-lookup"><span data-stu-id="47609-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="47609-220">Il codice di esempio seguente usa un formato di messaggio non standard</span><span class="sxs-lookup"><span data-stu-id="47609-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="47609-221">dove `cipher_algorithm_id` gli `hmac_algorithm_id` identificatori e gli identificatori di algoritmo sono rappresentazioni locali dell'applicazione (non standard) di tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="47609-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="47609-222">Questi identificatori possono avere senso in altre parti del protocollo di messaggistica esistente anziché come un flusso di byte concatenato a livello bare.</span><span class="sxs-lookup"><span data-stu-id="47609-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="47609-223">In questo esempio viene inoltre utilizzata una singola chiave master per derivare sia una chiave di crittografia che una chiave HMAC.</span><span class="sxs-lookup"><span data-stu-id="47609-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="47609-224">Questo viene fornito sia per comodità per trasformare un'applicazione con chiave in modo singly in un'applicazione dual-keyed, sia per incoraggiare a mantenere le due chiavi come valori diversi.</span><span class="sxs-lookup"><span data-stu-id="47609-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="47609-225">Garantisce inoltre che la chiave HMAC e la chiave di crittografia non possano uscire dalla sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="47609-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="47609-226">In questo esempio non <xref:System.IO.Stream> viene accettato un per la crittografia o la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="47609-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="47609-227">Il formato dati corrente rende difficile `hmac_tag` la crittografia a un passaggio perché il valore precede il testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="47609-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="47609-228">Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi di dimensioni fisse all'inizio per mantenere il parser più semplice.</span><span class="sxs-lookup"><span data-stu-id="47609-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="47609-229">Con questo formato di dati, è possibile la decrittografia un passaggio, anche se un implementatore viene avvertito di chiamare GetHashAndReset e verificare il risultato prima di chiamare TransformFinalBlock.With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="47609-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="47609-230">Se la crittografia di streaming è importante, potrebbe essere necessaria una modalità AE diversa.</span><span class="sxs-lookup"><span data-stu-id="47609-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
