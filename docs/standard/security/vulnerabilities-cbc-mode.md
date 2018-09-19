---
title: Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC con spaziatura interna
description: Informazioni su come rilevare e attenuare le vulnerabilità di temporizzazione con decrittografia simmetrica modalità Cipher Block Chaining (CBC) usando il riempimento.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: 6d16b6849bfd4744f1828cda38a537f842243c1d
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288381"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="1cfb5-103">Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC con spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="1cfb5-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="1cfb5-104">Microsoft ritiene che non è più sicuro decrittografare i dati crittografati con la modalità Cipher Block Chaining (CBC) dalla crittografia simmetrica quando verificabile riempimento viene applicato senza prima verificare l'integrità del testo crittografato, ad eccezione di molto specifico circostanze.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="1cfb5-105">Questa decisione si basa nella ricerca crittografica attualmente nota.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-105">This judgement is based on currently known cryptographic research.</span></span> 

## <a name="introduction"></a><span data-ttu-id="1cfb5-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="1cfb5-106">Introduction</span></span>

<span data-ttu-id="1cfb5-107">Un attacco di oracle spaziatura interna è un tipo di attacco contro i dati crittografati che consente l'autore dell'attacco decrittografare il contenuto dei dati, senza conoscere la chiave.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="1cfb5-108">Oracle fa riferimento a un "informazioni" che vengono fornite informazioni che l'azione che l'esecuzione sia corretto o meno un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="1cfb5-109">Si immagini una bacheca a cui è assegnato o di schede di gioco con un elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="1cfb5-110">Quando volto illumina con uno smile big perché sta guardando Lei è sta per effettuare uno spostamento ottimo, ovvero oracle.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-110">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="1cfb5-111">È, come l'avversario, possibile utilizzare questo oracle per pianificare il passaggio successivo in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="1cfb5-112">Spaziatura interna è un termine di crittografia specifico.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="1cfb5-113">Alcuni crittografie, che sono gli algoritmi utilizzati per crittografare i dati, di lavoro su blocchi di dati in cui ogni blocco corrisponde a una dimensione fissa.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="1cfb5-114">Se i dati da crittografare non sono le dimensioni corrette per riempire i blocchi, i dati vengono inseriti fino a quando non avviene.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="1cfb5-115">Molte forme di spaziatura interna richiedono tale riempimento sia sempre presente, anche se l'input originale era della dimensione appropriata.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="1cfb5-116">In questo modo la spaziatura interna da sempre essere rimosso senza problemi dopo la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="1cfb5-117">Combinando le due operazioni, un'implementazione del software con un riempimento di oracle, viene visualizzata se i dati decrittografati dispone di spaziatura interna valida.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="1cfb5-118">Oracle può essere semplici come restituire un valore con la dicitura "Riempimento non è valido" o qualcosa di più complicato simile all'esecuzione di un'ora misurabile diversa per l'elaborazione di un blocco valido invece di un blocco non valido.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="1cfb5-119">Le crittografie a blocchi dispongono di un'altra proprietà, denominata la modalità, che determina la relazione tra i dati nel primo blocco per i dati nel secondo blocco, e così via.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="1cfb5-120">Una delle modalità di uso più comune è CBC.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="1cfb5-121">CBC introduce un blocco di casuale iniziale, noto come il vettore di inizializzazione (IV) e combina il blocco precedente con il risultato della crittografia statica per fare in modo che la crittografia del messaggio stesso con la stessa chiave non sempre produce lo stesso output crittografato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="1cfb5-122">Un utente malintenzionato può usare un oracle di spaziatura interna, in combinazione con la modalità CBC dati strutturati, per inviare messaggi leggermente modificati per il codice che espone il oracle e continuare a inviare i dati fino a quando non lo oracle informa i dati siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="1cfb5-123">Da questa risposta, l'autore dell'attacco può decrittografare il messaggio byte per byte.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="1cfb5-124">Reti di computer moderni sono di qualità talmente elevata che un utente malintenzionato può rilevare molto piccolo (meno di 0,1 ms) le differenze nell'esecuzione di tempo nei sistemi remoti.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="1cfb5-125">Le applicazioni che si presuppone che una volta completata la decrittazione può essere eseguiti solo quando i dati non è stato manomesso potrebbero essere vulnerabile agli attacchi provenienti da strumenti progettati per osservare le differenze nelle riusciti e la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-125">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="1cfb5-126">Sebbene questa differenza di intervallo può essere più significativa in alcune lingue o in librerie rispetto ad altri, ora che si ritiene che si tratta di una minaccia pratica per tutti i linguaggi e librerie quando la risposta dell'applicazione all'errore viene preso in considerazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="1cfb5-127">Questo tipo di attacco si basa sulla possibilità di modificare i dati crittografati e testare il risultato con oracle.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="1cfb5-128">L'unico modo completamente attenuare l'attacco è per rilevare le modifiche apportate ai dati crittografati e rifiuta di eseguire azioni su di esso.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="1cfb5-129">Il metodo standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima di tutte le operazioni vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="1cfb5-130">La firma deve essere verificabile, non può essere creato dall'autore dell'attacco, in caso contrario, si potrebbe modificare i dati crittografati e quindi calcolare una firma di nuovo i dati modificati in base.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="1cfb5-131">Un tipo comune di firma appropriata è noto come un codice di autenticazione del messaggio hash con chiavi (HMAC).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="1cfb5-132">Un HMAC è diverso da un checksum in quanto richiede una chiave privata, nota solo all'utente che produce il valore HMAC e alla persona convalidarlo.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="1cfb5-133">Senza il possesso della chiave, non è possibile produrre un HMAC corretto.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="1cfb5-134">Quando si riceveranno i dati, si potrebbe richiedere i dati crittografati, in modo indipendente di calcolo di HMAC di code con la chiave privata è e la condivisione di mittente, quindi confronta il valore HMAC sono inviati rispetto a quella calcolato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="1cfb5-135">Questo confronto deve essere tempo costante, in caso contrario, è stato aggiunto un altro oracle rilevabili, che consente un tipo diverso di attacco.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="1cfb5-136">In sintesi, utilizzare riempito crittografie a blocchi CBC in modo sicuro, è necessario combinarli con un codice HMAC (o un altro controllo di integrità dei dati) da convalidare mediante un confronto tempo costante prima di tentare di decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="1cfb5-137">Poiché tutti i messaggi modificati sfruttare la stessa quantità di tempo per produrre una risposta, l'attacco non è consentita.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="1cfb5-138">Chi è vulnerabili</span><span class="sxs-lookup"><span data-stu-id="1cfb5-138">Who is vulnerable</span></span>

<span data-ttu-id="1cfb5-139">Si applica questa vulnerabilità per le applicazioni gestite e native che eseguono le proprie crittografia e decrittografia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="1cfb5-140">Questo include, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-140">This includes, for example:</span></span>

- <span data-ttu-id="1cfb5-141">Un'applicazione che consente di crittografare un cookie per la decrittografia successiva nel server.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="1cfb5-142">Un'applicazione di database che consente agli utenti di inserire dati in una tabella le cui colonne vengono decrittografati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="1cfb5-143">Un'applicazione di trasferimento di dati che si basa sulla crittografia mediante una chiave condivisa per proteggere i dati in transito.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="1cfb5-144">Un'applicazione che crittografa e decrittografa i messaggi "del tunnel TLS interno".</span><span class="sxs-lookup"><span data-stu-id="1cfb5-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="1cfb5-145">Si noti che tramite TLS da sola potrebbe non proteggere è in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="1cfb5-146">Un'applicazione vulnerabile:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-146">A vulnerable application:</span></span>

- <span data-ttu-id="1cfb5-147">Decrittografa i dati usando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio X.923 ANSI o PKCS #7.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="1cfb5-148">Esegue la decrittografia senza dopo aver eseguito un controllo di integrità dei dati (tramite un MAC o asimmetrici della firma digitale).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="1cfb5-149">Questo vale anche per le applicazioni basate su astrazioni sopra di questi tipi primitivi, ad esempio la struttura di EnvelopedData Cryptographic Message Syntax (PKCS #7 o CMS).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="1cfb5-150">Aree problematiche correlate</span><span class="sxs-lookup"><span data-stu-id="1cfb5-150">Related areas of concern</span></span>

<span data-ttu-id="1cfb5-151">Research ha portato a Microsoft di essere ulteriormente interessati relative ai messaggi CBC vengono riempiti con spaziatura interna quando il messaggio ha una struttura di un piè di pagina noto o stimabile 10126 ISO equivalenti.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="1cfb5-152">Ad esempio, il contenuto preparato in base alle regole di W3C XML Encryption Syntax and Processing raccomandazione (xmlenc, EncryptedXml).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="1cfb5-153">Mentre le linee guida W3C per firmare il messaggio, quindi crittografare ritenuta opportuno al momento, a questo punto è consigliabile eseguire sempre encrypt-then-sign.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="1cfb5-154">Gli sviluppatori di applicazioni dovrebbero sempre tenere verifica l'applicabilità di una chiave di firma asimmetrico, perché non vi è alcuna relazione di trust inerente tra una chiave asimmetrica e un messaggio arbitrario.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="1cfb5-155">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1cfb5-155">Details</span></span>

<span data-ttu-id="1cfb5-156">In passato, si è verificato il consenso che è importante crittografare e autenticare i dati importanti tramite mezzi, ad esempio le firme RSA o HMAC.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="1cfb5-157">Tuttavia, sono stati meno indicazioni chiare istruzioni eseguire la sequenziazione di operazioni di crittografia e autenticazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="1cfb5-158">A causa di vulnerabilità descritta in questo articolo, linee guida di Microsoft è a questo punto usare sempre il paradigma delle "encrypt-then-sign".</span><span class="sxs-lookup"><span data-stu-id="1cfb5-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="1cfb5-159">Vale a dire prima crittografare i dati utilizzando una chiave simmetrica, quindi calcolare una firma asimmetrica o il MAC tramite il testo crittografato (dati crittografati).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="1cfb5-160">Quando la decrittografia dei dati, eseguire l'operazione inversa.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="1cfb5-161">In primo luogo, verificare che il MAC o la firma del testo crittografato, quindi decrittografarlo.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="1cfb5-162">Classe di vulnerabilità note come "padding attacchi oracle" sono certo noti per esiste da oltre 10 anni.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="1cfb5-163">Le vulnerabilità consentono un attacco decrittografare i dati crittografati con gli algoritmi di blocchi simmetriche, ad esempio AES e 3DES, utilizzando non più di 4096 tentativi per ogni blocco di dati.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="1cfb5-164">Apportare queste vulnerabilità sfrutta il fatto che bloccano le crittografie vengono in genere usati con i dati di spaziatura interna verificabile alla fine.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="1cfb5-165">È stato rilevato che se un utente malintenzionato può manomettere testo crittografato e scoprire se la manomissione causa un errore nel formato di riempimento alla fine, l'autore dell'attacco può decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="1cfb5-166">Inizialmente, attacchi pratici in base ai servizi che restituiscono i codici di errore diverso basati sul fatto che la spaziatura interna è stata valida, ad esempio la vulnerabilità in ASP.NET [MS10 070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="1cfb5-167">Tuttavia, Microsoft ritiene ora che è pratico per condurre attacchi simili che utilizzano solo le differenze nell'intervallo tra l'elaborazione di spaziatura interna valida e non è valida.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="1cfb5-168">Condizione che lo schema di crittografia Usa una firma e che viene eseguita la verifica della firma con un runtime predefinito per una determinata lunghezza dei dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza la creazione di qualsiasi informazione da un autore dell'attacco tramite un [canale lato](https://en.wikipedia.org/wiki/Side-channel_attack).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="1cfb5-169">Poiché il controllo dell'integrità rifiuta eventuali messaggi alterati, la minaccia di oracle spaziatura interna è stata risolta.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="1cfb5-170">Materiale sussidiario</span><span class="sxs-lookup"><span data-stu-id="1cfb5-170">Guidance</span></span>

<span data-ttu-id="1cfb5-171">Prima di tutto, è consigliabile che tutti i dati con riservatezza devono essere trasmessa tramite sicurezza TLS (Transport Layer), il successore di Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="1cfb5-172">Successivamente, analizzare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="1cfb5-173">Comprendere esattamente quali crittografia che si sta eseguendo e quali la crittografia viene fornita tramite le piattaforme e le API in uso.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="1cfb5-174">Essere certi che ogni utilizzo a ogni livello di simmetrica [algoritmo di crittografia a blocchi](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), ad esempio AES e 3DES in modalità CBC incorporare l'uso di un controllo di integrità dei dati con chiave basata sul segreto (una firma asimmetrico, un HMAC, o per modificare la modalità di crittografia da un' [autenticato crittografia](https://en.wikipedia.org/wiki/Authenticated_encryption) modalità (AE), ad esempio GCM o CCM).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="1cfb5-175">In base alla ricerca corrente, in genere che si ritiene che quando vengono eseguiti i passaggi di autenticazione e crittografia in modo indipendente per le modalità non-AE della crittografia, il testo crittografato di autenticazione (encrypt-then-sign) è l'opzione generale migliore.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="1cfb5-176">Tuttavia, nessuna risposta corretta una soluzione universale per la crittografia e la generalizzazione non è consigli analoga a quella diretti di un crittografo professionale.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="1cfb5-177">Le applicazioni che non è possibile modificare il formato di messaggistica senza eseguire la decrittografia CBC non autenticata sono invitate a provare a integrare soluzioni di attenuazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="1cfb5-178">Decrittografare senza consentire il componente di decrittografia verificare o rimuovere la spaziatura interna:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="1cfb5-179">Eventuali spaziature interne che è stata applicata devono comunque essere rimossi o ignorati, che si desidera spostare il carico di lavoro nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="1cfb5-180">Il vantaggio è che la verifica di spaziatura interna e la rimozione possono essere incorporate in altra logica di verifica dei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="1cfb5-181">Se la verifica di spaziatura interna e la verifica dei dati possono essere eseguite in un tempo costante, viene ridotta la minaccia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="1cfb5-182">Poiché l'interpretazione della spaziatura interna viene modificata la lunghezza del messaggio rilevate, è comunque possibile informazioni sugli intervalli generate da questo approccio.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="1cfb5-183">Modificare la modalità di riempimento di decrittografia per ISO10126:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="1cfb5-184">Spaziatura interna di decrittografia ISO10126 è compatibile con spaziatura interna di crittografia PKCS7 e ANSIX923 spaziatura interna di crittografia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="1cfb5-185">Modifica della modalità riduce la Knowledge Base oracle spaziatura interna a 1 byte anziché l'intero blocco.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="1cfb5-186">Tuttavia, se il contenuto presenta un piè di pagina ben noti, ad esempio un'elemento XML, di chiusura attacchi correlati possono continuare a attacco contro il resto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="1cfb5-187">Ciò non impedisce anche ripristino plaintext in situazioni in cui l'autore dell'attacco può assegnare lo stesso testo non deve essere crittografato più volte con un offset di messaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="1cfb5-188">La valutazione di una chiamata di decrittografia per limitare il segnale di temporizzazione gate:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="1cfb5-189">Il calcolo del tempo di attesa deve avere un minimo che supererà la quantità massima di tempo che richiederebbe l'operazione di decrittografia per qualsiasi segmento di dati contenente la spaziatura interna.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="1cfb5-190">Calcoli ora devono essere eseguiti seguendo le istruzioni riportate in [acquisizione timestamp ad alta risoluzione](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), non tramite <xref:System.Environment.TickCount?displayProperty=nameWithType> (soggetto a roll-over/overflow) o la sottrazione di due timestamp di sistema (soggetti a modifica NTP errori).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="1cfb5-191">Calcoli ora devono essere con strumenti per l'operazione di decrittografia tra cui tutte le potenziali eccezioni in gestito o applicazioni C++, non solo aggiunti alla fine.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="1cfb5-192">Se l'esito positivo o negativo è ancora stato determinato, l'attività di controllo dell'intervallo deve restituire errori dopo la scadenza.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="1cfb5-193">Servizi che eseguono la decrittografia non autenticata devono avere il monitoraggio in modo che possano rilevare che è stato trovato un flusso eccessivo di messaggi "non è validi".</span><span class="sxs-lookup"><span data-stu-id="1cfb5-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="1cfb5-194">Tenere presente che questo segnale riporta falsi positivi (legittimamente danneggiato i dati) e falsi negativi (diffondendo l'attacco in un tempo sufficientemente lungo per eludere il rilevamento).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="1cfb5-195">Ricerca di codice vulnerabile - applicazioni native</span><span class="sxs-lookup"><span data-stu-id="1cfb5-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="1cfb5-196">Per i programmi compilati con la crittografia di Windows: raccolta Next Generation (CNG):</span><span class="sxs-lookup"><span data-stu-id="1cfb5-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="1cfb5-197">La chiamata di decrittografia riguarda [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specificando il `BCRYPT_BLOCK_PADDING` flag.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="1cfb5-198">L'handle di chiave è stato inizializzato chiamando [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) impostato su `BCRYPT_CHAIN_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="1cfb5-199">Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non aver assegnato alcun valore per `BCRYPT_CHAINING_MODE`.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="1cfb5-200">Per i programmi compilati con l'API di crittografia di Windows precedenti:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="1cfb5-201">La chiamata di decrittografia riguarda [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con `Final=TRUE`.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="1cfb5-202">L'handle di chiave è stato inizializzato chiamando [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) impostato su `CRYPT_MODE_CBC`.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="1cfb5-203">Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non aver assegnato alcun valore per `KP_MODE`.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="1cfb5-204">Ricerca codice vulnerabile - applicazioni gestite</span><span class="sxs-lookup"><span data-stu-id="1cfb5-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="1cfb5-205">La chiamata di decrittografia è per il <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> oppure <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> metodi su <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="1cfb5-206">Questo include i seguenti tipi derivati all'interno di .NET, ma può anche includere tipi di terze parti:</span><span class="sxs-lookup"><span data-stu-id="1cfb5-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="1cfb5-207">Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà è stata impostata <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="1cfb5-208">Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice potrebbe non aver assegnato i <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="1cfb5-209">Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà è stata impostata <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1cfb5-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="1cfb5-210">Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice potrebbe non aver assegnato i <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="1cfb5-211">Ricerca di codice vulnerabile - sintassi dei messaggi crittografati</span><span class="sxs-lookup"><span data-stu-id="1cfb5-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="1cfb5-212">Un messaggio CMS EnvelopedData non autenticato, il cui contenuto crittografato Usa la modalità CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7) e 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) è vulnerabile, nonché come messaggi tramite altri algoritmi di crittografia di blocco in modalità CBC.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="1cfb5-213">Anche se crittografie di flusso non sono soggette a questa vulnerabilità particolare, Microsoft consiglia sempre l'autenticazione i dati attraverso il valore ContentEncryptionAlgorithm ispezione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="1cfb5-214">Per le applicazioni gestite, EnvelopedData un CMS blob possono essere rilevati per qualsiasi valore che viene passato al <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="1cfb5-215">Per le applicazioni native, può essere rilevato un blob EnvelopedData CMS come qualsiasi valore fornito a un handle CMS tramite [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) cui risultante [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) è `CMSG_ENVELOPED` e/o l'handle CMS è in un secondo momento è stato inviato un `CMSG_CTRL_DECRYPT` istruzione tramite [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span><span class="sxs-lookup"><span data-stu-id="1cfb5-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="1cfb5-216">Esempio di codice vulnerabile - gestito</span><span class="sxs-lookup"><span data-stu-id="1cfb5-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="1cfb5-217">Questo metodo legge un cookie e li decrittografa e nessun controllo di integrità dei dati è visibile.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="1cfb5-218">Pertanto, il contenuto di un cookie che viene letto da questo metodo può essere attaccato dall'utente che lo ha ricevuto o da qualsiasi utente malintenzionato ha ottenuto il valore del cookie crittografato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="1cfb5-219">Esempio di codice di esempio riportate alcune procedure consigliate - gestiti</span><span class="sxs-lookup"><span data-stu-id="1cfb5-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="1cfb5-220">Esempio di codice seguente usa il formato messaggi non standard</span><span class="sxs-lookup"><span data-stu-id="1cfb5-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="1cfb5-221">in cui il `cipher_algorithm_id` e `hmac_algorithm_id` identificatori di algoritmi sono locali dell'applicazione (non standard) rappresentazioni di tali algoritmi.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="1cfb5-222">Questi identificatori possono avere senso in altre parti del protocollo di messaggistica esistente anziché come un bare bytestream concatenati.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="1cfb5-223">In questo esempio Usa anche una singola chiave master per derivare una chiave di crittografia sia una chiave HMAC.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="1cfb5-224">Entrambi per maggiore praticità viene fornito per l'attivazione di un'applicazione singolarmente con chiave fornita in un'applicazione con chiave dual e a incoraggiare mantenendo le due chiavi di diversi valori.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="1cfb5-225">Garantisce inoltre che la chiave HMAC e chiave di crittografia non perdano la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="1cfb5-226">In questo esempio non accetta un <xref:System.IO.Stream> per la crittografia o decrittografia.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="1cfb5-227">Crittografare difficile la rende di formato di dati un passaggio corrente perché il `hmac_tag` valore precede il testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="1cfb5-228">Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi di dimensioni fisse di inizio per mantenere più semplice il parser.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="1cfb5-229">Con questo formato di dati, un passaggio decrypt è possibile, anche se un responsabile dell'implementazione viene avvisati chiamare GetHashAndReset e verificare il risultato prima di chiamare TransformFinalBlock.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="1cfb5-230">Se la crittografia di streaming è importante, quindi una diversa modalità di Always Encrypted potrebbe essere necessaria.</span><span class="sxs-lookup"><span data-stu-id="1cfb5-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

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
