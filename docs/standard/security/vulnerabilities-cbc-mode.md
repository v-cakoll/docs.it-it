---
title: Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento
description: Informazioni su come rilevare e limitare le vulnerabilità di temporizzazione con decrittografia simmetrica modalità Cipher Block Chaining (CBC) usando il riempimento.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: a07acbb943c430f6e26bec44f55a5c84306da513
ms.sourcegitcommit: 73a662360bbe2f43c19aca1fbcc2565025c60cd8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2018
ms.locfileid: "35327454"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="f3aa3-103">Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento</span><span class="sxs-lookup"><span data-stu-id="f3aa3-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="f3aa3-104">Microsoft, in base a ricerca crittografica attualmente nota, ritiene che, ad eccezione di circostanze molto specifiche, non è più sicuro decrittografare i dati crittografati con la modalità Cipher Block Chaining (CBC) di crittografia simmetrica quando è stata riempimento verificabile applicate senza prima verificare l'integrità del testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-104">Microsoft, based on currently known cryptographic research, believes that, except for very specific circumstances, it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext.</span></span>

## <a name="introduction"></a><span data-ttu-id="f3aa3-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="f3aa3-105">Introduction</span></span>

<span data-ttu-id="f3aa3-106">Un attacco di spaziatura interna oracle è un tipo di attacco contro i dati crittografati che consente l'autore dell'attacco decrittografare il contenuto dei dati, senza conoscere la chiave.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-106">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="f3aa3-107">Oracle fa riferimento a un "sapere" che fornisce informazioni che l'azione di esse è in esecuzione sia corretto o meno un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-107">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="f3aa3-108">Si supponga la riproduzione di una scheda o una scheda di gioco con un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-108">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="f3aa3-109">Quando il tipo di carattere diventa attivo con uno smile big perché che ritiene Mary è sta per effettuare un buon spostamento, ovvero oracle.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-109">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="f3aa3-110">È, come l'avversario, possibile utilizzare questo oracle per pianificare la migrazione successiva nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-110">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="f3aa3-111">Il riempimento è un termine di cryptographic specifico.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-111">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="f3aa3-112">Alcuni crittografie, che sono gli algoritmi utilizzati per crittografare i dati, utilizzare blocchi di dati in cui ogni blocco ha una dimensione fissa.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-112">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="f3aa3-113">Se i dati da crittografare non sono della dimensione giusta per riempire i blocchi, i dati verranno aggiunti fino a quando non avviene.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-113">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="f3aa3-114">Molte forme di spaziatura interna richiedono la spaziatura interna da essere sempre presente, anche se l'input originale non è di dimensioni corrette.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-114">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="f3aa3-115">In questo modo la spaziatura interna sempre in modo sicuro da rimuovere durante la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-115">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="f3aa3-116">Inserisce i due elementi insieme, un'implementazione del software con un riempimento oracle, viene visualizzato se i dati decrittografati hanno riempimento valido.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-116">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="f3aa3-117">Oracle potrebbe essere semplici come restituendo un valore che indica "Riempimento non valido" o un attributo più complicato simile all'esecuzione di un'ora misurabile diversa per l'elaborazione di un blocco valido anziché un blocco non valido.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-117">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="f3aa3-118">Basato su blocchi crittografie dispongono di un'altra proprietà, denominata la modalità che determina la relazione tra i dati nel primo blocco ai dati nel secondo blocco, e così via.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-118">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="f3aa3-119">Una delle modalità di uso più comune è CBC.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-119">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="f3aa3-120">CBC introduce un blocco di casuale iniziale, noto come il vettore di inizializzazione (IV), parte e combina il blocco precedente con il risultato della crittografia statica per semplificare tale che la crittografia del messaggio stesso con la stessa chiave non produce sempre lo stesso output crittografato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-120">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="f3aa3-121">Un utente malintenzionato può usare un oracle riempimento, in combinazione con la modalità CBC dati strutturati, per inviare messaggi leggermente modificati per il codice che espone il oracle e mantenere l'invio dei dati fino a quando non oracle informa i dati siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-121">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="f3aa3-122">Da questa risposta, l'autore dell'attacco può decrittografare il messaggio byte per byte.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-122">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="f3aa3-123">Le reti moderno computer sono di qualità talmente elevata che un utente malintenzionato in grado di rilevare molto piccoli (meno 0,1 ms) ora differenze di esecuzione nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-123">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="f3aa3-124">Le applicazioni che si presuppone che una volta completata la decrittazione può avvenire solo quando i dati non è stato manomesso potrebbero essere vulnerabile agli attacchi da strumenti progettati in modo da osservare le differenze nelle decrittografia esito positivo e negativo.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-124">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="f3aa3-125">Anche questa differenza temporale può essere più significativa in alcune lingue o librerie di altri utenti, è ora sembrano che si tratta di una minaccia pratica per tutte le lingue e le librerie quando la risposta dell'applicazione all'errore viene presa in considerazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-125">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="f3aa3-126">Questo attacco si basa sulla possibilità di modificare i dati crittografati e verificare il risultato con oracle.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-126">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="f3aa3-127">L'unico modo per completamente attenuare l'attacco è per rilevare le modifiche apportate ai dati crittografati e rifiuta di eseguire azioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-127">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="f3aa3-128">La modalità standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima di eseguono qualsiasi operazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-128">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="f3aa3-129">La firma deve essere verificabile, non può essere creata dall'autore dell'attacco, in caso contrario, si sarebbe modificare i dati crittografati, quindi una nuova firma basata sui dati modificati di calcolo.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-129">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="f3aa3-130">Un tipo comune di firma appropriata è noto come un hash con chiave message authentication code (HMAC).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-130">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="f3aa3-131">Un HMAC è diverso da un checksum impiegati una chiave privata, nota solo alla persona che produce il valore HMAC e alla persona convalidarlo.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-131">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="f3aa3-132">Senza il possesso della chiave, è Impossibile produrre un codice HMAC corretto.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-132">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="f3aa3-133">Quando si riceveranno i dati, si sarebbe di calcolo in modo indipendente il valore HMAC con la chiave privata utente e la condivisione di mittente, quindi confronta il valore HMAC sono inviati rispetto a quella calcolato, richiedere i dati crittografati.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-133">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="f3aa3-134">Questo confronto debba essere tempo costante, in caso contrario aver aggiunto un altro oracle rilevabili, consentendo un tipo diverso di attacco.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-134">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="f3aa3-135">In sintesi, utilizzare applicato un riempimento le crittografie a blocchi CBC in modo sicuro, è necessario combinarle con un codice HMAC (o un altro controllo di integrità dei dati) è convalidare mediante un confronto tempo costante prima di tentare di decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-135">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="f3aa3-136">Poiché tutti i messaggi modificati richiedono la stessa quantità di tempo per produrre una risposta, viene impedita l'attacco.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-136">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="f3aa3-137">Chi è vulnerabile</span><span class="sxs-lookup"><span data-stu-id="f3aa3-137">Who is vulnerable</span></span>

<span data-ttu-id="f3aa3-138">Questa vulnerabilità si applica alle applicazioni native e non gestite che stanno eseguendo i propri crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-138">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="f3aa3-139">Sono inclusi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-139">This includes, for example:</span></span>

- <span data-ttu-id="f3aa3-140">Un'applicazione che consente di crittografare un cookie per la decrittografia successive nel server.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-140">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="f3aa3-141">Un'applicazione di database che offre la possibilità agli utenti di inserire dati in una tabella le cui colonne vengono decrittografate in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-141">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="f3aa3-142">Applicazione di trasferimento dei dati che si basa su crittografia usando una chiave condivisa per proteggere i dati in transito.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-142">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="f3aa3-143">Un'applicazione che crittografa e decrittografa i messaggi "del tunnel TLS interno".</span><span class="sxs-lookup"><span data-stu-id="f3aa3-143">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="f3aa3-144">Si noti che tramite TLS solo potrebbe non proteggere in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-144">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="f3aa3-145">Un'applicazione vulnerabile:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-145">A vulnerable application:</span></span>

- <span data-ttu-id="f3aa3-146">Decrittografa i dati usando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio X.923 ANSI o PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-146">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="f3aa3-147">Esegue la decrittografia senza aver eseguito un controllo di integrità dei dati (tramite un MAC o asimmetrici della firma digitale).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-147">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="f3aa3-148">Questo vale anche per le applicazioni compilate sopra le astrazioni di sopra di questi tipi di primitivi, ad esempio la struttura EnvelopedData di Cryptographic Message Syntax (PKCS #7/CMS).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-148">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="f3aa3-149">Aree problematiche correlate</span><span class="sxs-lookup"><span data-stu-id="f3aa3-149">Related areas of concern</span></span>

<span data-ttu-id="f3aa3-150">Research ha portato Microsoft possono essere ulteriormente interessate relative ai messaggi CBC vengono riempiti con spaziatura durante il messaggio ha una struttura ben noto o stimabile piè di pagina 10126 ISO equivalenti.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-150">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="f3aa3-151">Ad esempio, il contenuto preparato in base alle regole del W3C XML Encryption Syntax e indicazione di elaborazione (xmlenc, EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-151">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="f3aa3-152">Mentre le linee guida W3C per firmare il messaggio quindi crittografare ritenuta appropriata al momento, ora è consigliabile eseguire sempre encrypt-then-sign.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-152">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="f3aa3-153">Gli sviluppatori di applicazioni devono essere sempre presente verifica l'applicabilità di una chiave di firma asimmetrico, perché non vi è alcuna relazione di trust inerente tra una chiave asimmetrica e un messaggio arbitrario.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-153">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="f3aa3-154">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f3aa3-154">Details</span></span>

<span data-ttu-id="f3aa3-155">In passato, si è verificato il consenso che è importante crittografare e autenticare i dati importanti tramite mezzi, ad esempio le firme HMAC o RSA.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-155">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="f3aa3-156">Tuttavia, sono stati meno indicazioni chiare su come sequenza di operazioni di crittografia e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-156">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="f3aa3-157">A causa di vulnerabilità descritti in dettaglio in questo articolo, linee guida di Microsoft è ora di utilizzare sempre il paradigma "encrypt-then-sign".</span><span class="sxs-lookup"><span data-stu-id="f3aa3-157">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="f3aa3-158">Vale a dire prima crittografare i dati utilizzando una chiave simmetrica, quindi calcolare MAC o asimmetrici della firma il testo crittografato (dati crittografati).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-158">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="f3aa3-159">Quando la decrittografia dei dati, eseguire l'operazione inversa.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-159">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="f3aa3-160">In primo luogo, confermare il MAC o la firma del testo crittografato, quindi decrittografarlo.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-160">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="f3aa3-161">Una classe di vulnerabilità note come "padding attacchi oracle" Nota esistere per oltre 10 anni.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-161">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="f3aa3-162">Queste vulnerabilità consentono un attacco decrittografare i dati crittografati con gli algoritmi simmetrico, ad esempio AES e 3DES, utilizzando non più di 4096 tentativi per ogni blocco di dati.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-162">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="f3aa3-163">Apportare queste vulnerabilità uso del fatto che blocca le crittografie vengono spesso usati con i dati di spaziatura interna verificabile alla fine.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-163">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="f3aa3-164">È stato rilevato che se un utente malintenzionato può manomettere testo crittografato e determinare se la manomissione hanno causato l'errore nel formato del riempimento alla fine, l'autore dell'attacco può decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-164">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="f3aa3-165">Inizialmente, attacchi pratici in base ai servizi che restituirebbero i codici di errore diversi in base a seconda se il riempimento era valido, ad esempio la vulnerabilità in ASP.NET [MS10 070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-165">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="f3aa3-166">Tuttavia, Microsoft ritiene ora che è pratico eseguire attacchi simile utilizzando solo le differenze nell'intervallo tra l'elaborazione di spaziatura valido e non valido.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-166">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="f3aa3-167">Condizione che lo schema di crittografia utilizza una firma e che viene eseguita la verifica della firma con il runtime predefinito per una determinata lunghezza dei dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza la creazione di qualsiasi informazione da un autore dell'attacco tramite un [canale lato](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-167">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="f3aa3-168">Poiché il controllo dell'integrità rifiuta eventuali messaggi manomessi, viene ridotta la minaccia di oracle spaziatura interna.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-168">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="f3aa3-169">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="f3aa3-169">Guidance</span></span>

<span data-ttu-id="f3aa3-170">In primo luogo, è consigliabile che tutti i dati che dispone di riservatezza devono essere trasmesso sulla sicurezza TLS (Transport Layer), il successore a Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-170">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="f3aa3-171">Successivamente, analizzare l'applicazione e:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-171">Next, analyze your application to:</span></span>

- <span data-ttu-id="f3aa3-172">Comprendere e con precisione quali che si sta eseguendo la crittografia quali la crittografia viene fornita tramite piattaforme e le API in uso.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-172">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="f3aa3-173">Essere certi che ogni utilizzo di ogni livello di un simmetrica [algoritmo di crittografia di blocco](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), ad esempio AES e 3DES in modalità CBC incorporare l'utilizzo di un controllo di integrità dei dati con chiave basata sul segreto (asimmetrici della firma, un HMAC o per modificare la modalità di crittografia per un' [autenticato crittografia](https://en.wikipedia.org/wiki/Authenticated_encryption) modalità (AE), ad esempio GCM o CCM).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-173">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="f3aa3-174">In base alla ricerca corrente, in genere sembrano che quando vengono eseguiti i passaggi di autenticazione e crittografia in modo indipendente per le modalità non AE della crittografia, l'autenticazione il testo crittografato (encrypt-then-sign) è la migliore opzione generale.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-174">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="f3aa3-175">Tuttavia, nessuna risposta corretta giusto per la crittografia e questo generalizzazione non consigli analoga a quella diretto da un crittografo professionale.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-175">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="f3aa3-176">Le applicazioni che sono in grado di modificare il formato di messaggistica senza eseguire la decrittografia CBC non autenticata sono invitate a provare a incorporare le misure di prevenzione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-176">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="f3aa3-177">Decrittografia non sono consentite il componente di decrittografia verificare o rimuovere la spaziatura interna:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-177">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="f3aa3-178">Spaziatura interna che è stato applicato deve comunque essere rimossi o ignorati, se si spostano il carico di lavoro nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-178">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="f3aa3-179">Il vantaggio è che la verifica di spaziatura interna e la rimozione possono essere incorporate nel altri logica di verifica dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-179">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="f3aa3-180">Se la verifica di spaziatura interna e la verifica dei dati può essere eseguiti in un tempo costante, viene ridotto il rischio.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-180">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="f3aa3-181">Poiché l'interpretazione della spaziatura interna viene modificata la lunghezza del messaggio venga percepito, potrebbe comunque essere presenti le informazioni di temporizzazione inviate da questo approccio.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-181">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="f3aa3-182">Modificare la modalità di riempimento di decrittografia per ISO10126:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-182">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="f3aa3-183">Il riempimento di decrittografia ISO10126 è compatibile con il riempimento di crittografia PKCS7 e spaziatura interna crittografia ANSIX923.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-183">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="f3aa3-184">Modifica della modalità riduce la Knowledge Base oracle di spaziatura interna a 1 byte anziché l'intero blocco.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-184">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="f3aa3-185">Tuttavia, se il contenuto ha un piè di pagina noto, ad esempio un elemento XML, di chiusura attacchi correlati possono continuare attaccare il resto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-185">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="f3aa3-186">Questo inoltre non impedisce il ripristino di testo normale nelle situazioni in cui l'utente malintenzionato può assegnare lo stesso testo non crittografato di essere crittografato più volte con un offset di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-186">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="f3aa3-187">Controllare la valutazione di una chiamata di decrittografia per limitare il segnale di temporizzazione:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-187">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="f3aa3-188">Il calcolo del tempo di attesa deve avere almeno che superano la quantità massima di tempo l'operazione di decrittografia per qualsiasi segmento di dati che contiene la spaziatura interna.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-188">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="f3aa3-189">È necessario eseguire i calcoli di tempo in base alle indicazioni fornite in [acquisizione timestamp ad alta risoluzione](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), non tramite <xref:System.Environment.TickCount?displayProperty=nameWithType> (conformemente roll-over/overflow) o la sottrazione di due timestamp di sistema (soggetti a modifica NTP errori).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-189">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="f3aa3-190">I calcoli di tempo devono essere comprende l'operazione di decrittografia tra tutte le potenziali eccezioni in gestito o applicazioni C++, non solo aggiunti alla fine.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-190">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="f3aa3-191">Se l'esito positivo o negativo è ancora stato determinato, il controllo di intervallo deve restituire errori dopo la scadenza.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-191">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="f3aa3-192">Servizi che eseguono la decrittografia non autenticata devono disporre di monitoraggio per rilevare che un flusso eccessivo di messaggi "non validi" Torna.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-192">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="f3aa3-193">Tenere presente che questo segnale esegue falsi positivi (dati danneggiati legittimamente) e falsi negativi (diffusione attacco in un tempo sufficientemente lungo per eludere il rilevamento).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-193">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="f3aa3-194">Ricerca del codice vulnerabile - applicazioni native</span><span class="sxs-lookup"><span data-stu-id="f3aa3-194">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="f3aa3-195">Per i programmi compilati con la crittografia di Windows: libreria Next Generation (CNG):</span><span class="sxs-lookup"><span data-stu-id="f3aa3-195">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="f3aa3-196">La chiamata di decrittografia riguarda [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specificando il `BCRYPT_BLOCK_PADDING` flag.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-196">The decryption call is to [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="f3aa3-197">L'handle di chiave è stata inizializzata tramite una chiamata [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) con [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) impostato su `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-197">The key handle has been initialized by calling [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="f3aa3-198">Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non avere assegnato alcun valore per `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-198">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="f3aa3-199">Per i programmi compilati con l'API di crittografia di Windows precedenti:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-199">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="f3aa3-200">La chiamata di decrittografia riguarda [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) con `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-200">The decryption call is to [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) with `Final=TRUE`.</span></span>
- <span data-ttu-id="f3aa3-201">L'handle di chiave è stata inizializzata tramite una chiamata [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) con [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) impostato su `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-201">The key handle has been initialized by calling [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="f3aa3-202">Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non avere assegnato alcun valore per `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-202">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="f3aa3-203">Trovare codice vulnerabile - applicazioni gestite</span><span class="sxs-lookup"><span data-stu-id="f3aa3-203">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="f3aa3-204">La chiamata di decrittografia è per il <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> oppure <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> metodi su <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-204">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="f3aa3-205">Questo include i seguenti tipi derivati all'interno di .NET, ma può anche includere i tipi di terze parti:</span><span class="sxs-lookup"><span data-stu-id="f3aa3-205">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="f3aa3-206">Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-206">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="f3aa3-207">Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice non potrebbe mai stato assegnato il <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-207">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="f3aa3-208">Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f3aa3-208">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="f3aa3-209">Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice non potrebbe mai stato assegnato il <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-209">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="f3aa3-210">Ricerca del codice vulnerabile - sintassi dei messaggi crittografati</span><span class="sxs-lookup"><span data-stu-id="f3aa3-210">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="f3aa3-211">Un messaggio non autenticato CMS EnvelopedData il cui contenuto crittografato utilizza la modalità operativa CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) è vulnerabili, nonché come messaggi con altri algoritmi di crittografia di blocco in modalità CBC.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-211">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="f3aa3-212">Mentre alle crittografie a flussi non sono soggetti a questa vulnerabilità particolare, si consiglia di autenticazione sempre i dati su controllando il valore ContentEncryptionAlgorithm.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-212">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="f3aa3-213">Per le applicazioni gestite, una EnvelopedData CMS blob può essere rilevato come qualsiasi valore che viene passato a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-213">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="f3aa3-214">Per le applicazioni native, è possibile rilevare un blob CMS EnvelopedData come un valore fornito a un handle CMS tramite [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) cui risultante [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) è `CMSG_ENVELOPED` e/o l'handle CMS è in un secondo momento inviato un `CMSG_CTRL_DECRYPT` istruzione tramite [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3aa3-214">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) whose resulting [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="f3aa3-215">Nell'esempio di codice vulnerabile - gestito</span><span class="sxs-lookup"><span data-stu-id="f3aa3-215">Vulnerable code example - managed</span></span>

<span data-ttu-id="f3aa3-216">Questo metodo legge un cookie e li decrittografa e nessun controllo di integrità dei dati è visibile.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-216">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="f3aa3-217">Pertanto, il contenuto di un cookie che viene letto da questo metodo può essere attaccato dall'utente che ha ricevuto o da qualsiasi utente malintenzionato ha ottenuto il valore di cookie crittografato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-217">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="f3aa3-218">Esempio di codice di esempio consigliate - gestiti</span><span class="sxs-lookup"><span data-stu-id="f3aa3-218">Example code following recommended practices - managed</span></span>

<span data-ttu-id="f3aa3-219">Esempio di codice seguente viene utilizzato un formato del messaggio non standard</span><span class="sxs-lookup"><span data-stu-id="f3aa3-219">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="f3aa3-220">in cui il `cipher_algorithm_id` e `hmac_algorithm_id` identificatori di algoritmi sono locali dell'applicazione (standard) rappresentazioni di tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-220">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="f3aa3-221">Questi identificatori possono risultare utile in altre parti del protocollo di messaggistica esistente anziché come un bare bytestream concatenati.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-221">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="f3aa3-222">Questo esempio Usa anche una sola chiave master per derivare una chiave di crittografia sia una chiave HMAC.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-222">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="f3aa3-223">Viene fornito sia per maggiore praticità per l'attivazione di un'applicazione singolarmente codificati in un'applicazione con chiave basata sul doppio e incoraggiare mantenendo i valori come diversi le due chiavi.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-223">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="f3aa3-224">Garantisce inoltre che la chiave HMAC e chiave di crittografia non perdano la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-224">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="f3aa3-225">In questo esempio non accetta un <xref:System.IO.Stream> per la crittografia o decrittografia.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-225">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="f3aa3-226">L'imposta come corrente dei dati formato un passaggio crittografare difficile perché la `hmac_tag` valore precede il testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-226">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="f3aa3-227">Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi a dimensione fissa all'inizio di mantenere più semplice il parser.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-227">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="f3aa3-228">Con questo formato di dati, un passaggio decrypt è possibile, anche se un responsabile dell'implementazione viene avvisati da chiamare GetHashAndReset e verificare i risultati prima di chiamare TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-228">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="f3aa3-229">Se la crittografia di streaming è importante, una modalità diversa AE potrebbe essere necessario.</span><span class="sxs-lookup"><span data-stu-id="f3aa3-229">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
