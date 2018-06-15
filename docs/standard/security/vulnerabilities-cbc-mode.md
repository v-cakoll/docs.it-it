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
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento

Microsoft, in base a ricerca crittografica attualmente nota, ritiene che, ad eccezione di circostanze molto specifiche, non è più sicuro decrittografare i dati crittografati con la modalità Cipher Block Chaining (CBC) di crittografia simmetrica quando è stata riempimento verificabile applicate senza prima verificare l'integrità del testo crittografato.

## <a name="introduction"></a>Introduzione

Un attacco di spaziatura interna oracle è un tipo di attacco contro i dati crittografati che consente l'autore dell'attacco decrittografare il contenuto dei dati, senza conoscere la chiave.

Oracle fa riferimento a un "sapere" che fornisce informazioni che l'azione di esse è in esecuzione sia corretto o meno un utente malintenzionato. Si supponga la riproduzione di una scheda o una scheda di gioco con un elemento figlio. Quando il tipo di carattere diventa attivo con uno smile big perché che ritiene Mary è sta per effettuare un buon spostamento, ovvero oracle. È, come l'avversario, possibile utilizzare questo oracle per pianificare la migrazione successiva nel modo appropriato.

Il riempimento è un termine di cryptographic specifico. Alcuni crittografie, che sono gli algoritmi utilizzati per crittografare i dati, utilizzare blocchi di dati in cui ogni blocco ha una dimensione fissa. Se i dati da crittografare non sono della dimensione giusta per riempire i blocchi, i dati verranno aggiunti fino a quando non avviene. Molte forme di spaziatura interna richiedono la spaziatura interna da essere sempre presente, anche se l'input originale non è di dimensioni corrette. In questo modo la spaziatura interna sempre in modo sicuro da rimuovere durante la decrittografia.

Inserisce i due elementi insieme, un'implementazione del software con un riempimento oracle, viene visualizzato se i dati decrittografati hanno riempimento valido. Oracle potrebbe essere semplici come restituendo un valore che indica "Riempimento non valido" o un attributo più complicato simile all'esecuzione di un'ora misurabile diversa per l'elaborazione di un blocco valido anziché un blocco non valido.

Basato su blocchi crittografie dispongono di un'altra proprietà, denominata la modalità che determina la relazione tra i dati nel primo blocco ai dati nel secondo blocco, e così via. Una delle modalità di uso più comune è CBC. CBC introduce un blocco di casuale iniziale, noto come il vettore di inizializzazione (IV), parte e combina il blocco precedente con il risultato della crittografia statica per semplificare tale che la crittografia del messaggio stesso con la stessa chiave non produce sempre lo stesso output crittografato.

Un utente malintenzionato può usare un oracle riempimento, in combinazione con la modalità CBC dati strutturati, per inviare messaggi leggermente modificati per il codice che espone il oracle e mantenere l'invio dei dati fino a quando non oracle informa i dati siano corretti. Da questa risposta, l'autore dell'attacco può decrittografare il messaggio byte per byte.

Le reti moderno computer sono di qualità talmente elevata che un utente malintenzionato in grado di rilevare molto piccoli (meno 0,1 ms) ora differenze di esecuzione nei sistemi remoti. Le applicazioni che si presuppone che una volta completata la decrittazione può avvenire solo quando i dati non è stato manomesso potrebbero essere vulnerabile agli attacchi da strumenti progettati in modo da osservare le differenze nelle decrittografia esito positivo e negativo. Anche questa differenza temporale può essere più significativa in alcune lingue o librerie di altri utenti, è ora sembrano che si tratta di una minaccia pratica per tutte le lingue e le librerie quando la risposta dell'applicazione all'errore viene presa in considerazione.

Questo attacco si basa sulla possibilità di modificare i dati crittografati e verificare il risultato con oracle. L'unico modo per completamente attenuare l'attacco è per rilevare le modifiche apportate ai dati crittografati e rifiuta di eseguire azioni su di esso. La modalità standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima di eseguono qualsiasi operazione. La firma deve essere verificabile, non può essere creata dall'autore dell'attacco, in caso contrario, si sarebbe modificare i dati crittografati, quindi una nuova firma basata sui dati modificati di calcolo. Un tipo comune di firma appropriata è noto come un hash con chiave message authentication code (HMAC). Un HMAC è diverso da un checksum impiegati una chiave privata, nota solo alla persona che produce il valore HMAC e alla persona convalidarlo. Senza il possesso della chiave, è Impossibile produrre un codice HMAC corretto. Quando si riceveranno i dati, si sarebbe di calcolo in modo indipendente il valore HMAC con la chiave privata utente e la condivisione di mittente, quindi confronta il valore HMAC sono inviati rispetto a quella calcolato, richiedere i dati crittografati. Questo confronto debba essere tempo costante, in caso contrario aver aggiunto un altro oracle rilevabili, consentendo un tipo diverso di attacco.

In sintesi, utilizzare applicato un riempimento le crittografie a blocchi CBC in modo sicuro, è necessario combinarle con un codice HMAC (o un altro controllo di integrità dei dati) è convalidare mediante un confronto tempo costante prima di tentare di decrittografare i dati. Poiché tutti i messaggi modificati richiedono la stessa quantità di tempo per produrre una risposta, viene impedita l'attacco.

## <a name="who-is-vulnerable"></a>Chi è vulnerabile

Questa vulnerabilità si applica alle applicazioni native e non gestite che stanno eseguendo i propri crittografia e decrittografia. Sono inclusi, ad esempio:

- Un'applicazione che consente di crittografare un cookie per la decrittografia successive nel server.
- Un'applicazione di database che offre la possibilità agli utenti di inserire dati in una tabella le cui colonne vengono decrittografate in un secondo momento.
- Applicazione di trasferimento dei dati che si basa su crittografia usando una chiave condivisa per proteggere i dati in transito.
- Un'applicazione che crittografa e decrittografa i messaggi "del tunnel TLS interno".

Si noti che tramite TLS solo potrebbe non proteggere in questi scenari.

Un'applicazione vulnerabile:

- Decrittografa i dati usando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio X.923 ANSI o PKCS #7.
- Esegue la decrittografia senza aver eseguito un controllo di integrità dei dati (tramite un MAC o asimmetrici della firma digitale).

Questo vale anche per le applicazioni compilate sopra le astrazioni di sopra di questi tipi di primitivi, ad esempio la struttura EnvelopedData di Cryptographic Message Syntax (PKCS #7/CMS).

## <a name="related-areas-of-concern"></a>Aree problematiche correlate

Research ha portato Microsoft possono essere ulteriormente interessate relative ai messaggi CBC vengono riempiti con spaziatura durante il messaggio ha una struttura ben noto o stimabile piè di pagina 10126 ISO equivalenti. Ad esempio, il contenuto preparato in base alle regole del W3C XML Encryption Syntax e indicazione di elaborazione (xmlenc, EncryptedXml). Mentre le linee guida W3C per firmare il messaggio quindi crittografare ritenuta appropriata al momento, ora è consigliabile eseguire sempre encrypt-then-sign.

Gli sviluppatori di applicazioni devono essere sempre presente verifica l'applicabilità di una chiave di firma asimmetrico, perché non vi è alcuna relazione di trust inerente tra una chiave asimmetrica e un messaggio arbitrario.

## <a name="details"></a>Dettagli

In passato, si è verificato il consenso che è importante crittografare e autenticare i dati importanti tramite mezzi, ad esempio le firme HMAC o RSA. Tuttavia, sono stati meno indicazioni chiare su come sequenza di operazioni di crittografia e autenticazione. A causa di vulnerabilità descritti in dettaglio in questo articolo, linee guida di Microsoft è ora di utilizzare sempre il paradigma "encrypt-then-sign". Vale a dire prima crittografare i dati utilizzando una chiave simmetrica, quindi calcolare MAC o asimmetrici della firma il testo crittografato (dati crittografati). Quando la decrittografia dei dati, eseguire l'operazione inversa. In primo luogo, confermare il MAC o la firma del testo crittografato, quindi decrittografarlo.

Una classe di vulnerabilità note come "padding attacchi oracle" Nota esistere per oltre 10 anni. Queste vulnerabilità consentono un attacco decrittografare i dati crittografati con gli algoritmi simmetrico, ad esempio AES e 3DES, utilizzando non più di 4096 tentativi per ogni blocco di dati. Apportare queste vulnerabilità uso del fatto che blocca le crittografie vengono spesso usati con i dati di spaziatura interna verificabile alla fine. È stato rilevato che se un utente malintenzionato può manomettere testo crittografato e determinare se la manomissione hanno causato l'errore nel formato del riempimento alla fine, l'autore dell'attacco può decrittografare i dati.

Inizialmente, attacchi pratici in base ai servizi che restituirebbero i codici di errore diversi in base a seconda se il riempimento era valido, ad esempio la vulnerabilità in ASP.NET [MS10 070](https://technet.microsoft.com/library/security/ms10-070.aspx). Tuttavia, Microsoft ritiene ora che è pratico eseguire attacchi simile utilizzando solo le differenze nell'intervallo tra l'elaborazione di spaziatura valido e non valido.

Condizione che lo schema di crittografia utilizza una firma e che viene eseguita la verifica della firma con il runtime predefinito per una determinata lunghezza dei dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza la creazione di qualsiasi informazione da un autore dell'attacco tramite un [canale lato](https://en.wikipedia.org/wiki/Side-channel_attack). Poiché il controllo dell'integrità rifiuta eventuali messaggi manomessi, viene ridotta la minaccia di oracle spaziatura interna.

## <a name="guidance"></a>Materiale sussidiario

In primo luogo, è consigliabile che tutti i dati che dispone di riservatezza devono essere trasmesso sulla sicurezza TLS (Transport Layer), il successore a Secure Sockets Layer (SSL).

Successivamente, analizzare l'applicazione e:

- Comprendere e con precisione quali che si sta eseguendo la crittografia quali la crittografia viene fornita tramite piattaforme e le API in uso.
- Essere certi che ogni utilizzo di ogni livello di un simmetrica [algoritmo di crittografia di blocco](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), ad esempio AES e 3DES in modalità CBC incorporare l'utilizzo di un controllo di integrità dei dati con chiave basata sul segreto (asimmetrici della firma, un HMAC o per modificare la modalità di crittografia per un' [autenticato crittografia](https://en.wikipedia.org/wiki/Authenticated_encryption) modalità (AE), ad esempio GCM o CCM).

In base alla ricerca corrente, in genere sembrano che quando vengono eseguiti i passaggi di autenticazione e crittografia in modo indipendente per le modalità non AE della crittografia, l'autenticazione il testo crittografato (encrypt-then-sign) è la migliore opzione generale. Tuttavia, nessuna risposta corretta giusto per la crittografia e questo generalizzazione non consigli analoga a quella diretto da un crittografo professionale.

Le applicazioni che sono in grado di modificare il formato di messaggistica senza eseguire la decrittografia CBC non autenticata sono invitate a provare a incorporare le misure di prevenzione, ad esempio:

- Decrittografia non sono consentite il componente di decrittografia verificare o rimuovere la spaziatura interna:
  - Spaziatura interna che è stato applicato deve comunque essere rimossi o ignorati, se si spostano il carico di lavoro nell'applicazione.
  - Il vantaggio è che la verifica di spaziatura interna e la rimozione possono essere incorporate nel altri logica di verifica dei dati dell'applicazione. Se la verifica di spaziatura interna e la verifica dei dati può essere eseguiti in un tempo costante, viene ridotto il rischio.
  - Poiché l'interpretazione della spaziatura interna viene modificata la lunghezza del messaggio venga percepito, potrebbe comunque essere presenti le informazioni di temporizzazione inviate da questo approccio.
- Modificare la modalità di riempimento di decrittografia per ISO10126:
  - Il riempimento di decrittografia ISO10126 è compatibile con il riempimento di crittografia PKCS7 e spaziatura interna crittografia ANSIX923.
  - Modifica della modalità riduce la Knowledge Base oracle di spaziatura interna a 1 byte anziché l'intero blocco. Tuttavia, se il contenuto ha un piè di pagina noto, ad esempio un elemento XML, di chiusura attacchi correlati possono continuare attaccare il resto del messaggio.
  - Questo inoltre non impedisce il ripristino di testo normale nelle situazioni in cui l'utente malintenzionato può assegnare lo stesso testo non crittografato di essere crittografato più volte con un offset di messaggi diversi.
- Controllare la valutazione di una chiamata di decrittografia per limitare il segnale di temporizzazione:
  - Il calcolo del tempo di attesa deve avere almeno che superano la quantità massima di tempo l'operazione di decrittografia per qualsiasi segmento di dati che contiene la spaziatura interna.
  - È necessario eseguire i calcoli di tempo in base alle indicazioni fornite in [acquisizione timestamp ad alta risoluzione](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), non tramite <xref:System.Environment.TickCount?displayProperty=nameWithType> (conformemente roll-over/overflow) o la sottrazione di due timestamp di sistema (soggetti a modifica NTP errori).
  - I calcoli di tempo devono essere comprende l'operazione di decrittografia tra tutte le potenziali eccezioni in gestito o applicazioni C++, non solo aggiunti alla fine.
  - Se l'esito positivo o negativo è ancora stato determinato, il controllo di intervallo deve restituire errori dopo la scadenza.
- Servizi che eseguono la decrittografia non autenticata devono disporre di monitoraggio per rilevare che un flusso eccessivo di messaggi "non validi" Torna.
  - Tenere presente che questo segnale esegue falsi positivi (dati danneggiati legittimamente) e falsi negativi (diffusione attacco in un tempo sufficientemente lungo per eludere il rilevamento).

## <a name="finding-vulnerable-code---native-applications"></a>Ricerca del codice vulnerabile - applicazioni native

Per i programmi compilati con la crittografia di Windows: libreria Next Generation (CNG):

- La chiamata di decrittografia riguarda [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specificando il `BCRYPT_BLOCK_PADDING` flag.
- L'handle di chiave è stata inizializzata tramite una chiamata [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) con [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) impostato su `BCRYPT_CHAIN_MODE_CBC`.
  - Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non avere assegnato alcun valore per `BCRYPT_CHAINING_MODE`.

Per i programmi compilati con l'API di crittografia di Windows precedenti:

- La chiamata di decrittografia riguarda [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) con `Final=TRUE`.
- L'handle di chiave è stata inizializzata tramite una chiamata [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) con [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) impostato su `CRYPT_MODE_CBC`.
  - Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, interessata codice potrebbe non avere assegnato alcun valore per `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Trovare codice vulnerabile - applicazioni gestite

- La chiamata di decrittografia è per il <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> oppure <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> metodi su <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Questo include i seguenti tipi derivati all'interno di .NET, ma può anche includere i tipi di terze parti:
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
- Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice non potrebbe mai stato assegnato il <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà.
- Il <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, interessata codice non potrebbe mai stato assegnato il <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Ricerca del codice vulnerabile - sintassi dei messaggi crittografati

Un messaggio non autenticato CMS EnvelopedData il cui contenuto crittografato utilizza la modalità operativa CBC AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) è vulnerabili, nonché come messaggi con altri algoritmi di crittografia di blocco in modalità CBC.

Mentre alle crittografie a flussi non sono soggetti a questa vulnerabilità particolare, si consiglia di autenticazione sempre i dati su controllando il valore ContentEncryptionAlgorithm.

Per le applicazioni gestite, una EnvelopedData CMS blob può essere rilevato come qualsiasi valore che viene passato a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Per le applicazioni native, è possibile rilevare un blob CMS EnvelopedData come un valore fornito a un handle CMS tramite [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) cui risultante [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) è `CMSG_ENVELOPED` e/o l'handle CMS è in un secondo momento inviato un `CMSG_CTRL_DECRYPT` istruzione tramite [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).

## <a name="vulnerable-code-example---managed"></a>Nell'esempio di codice vulnerabile - gestito

Questo metodo legge un cookie e li decrittografa e nessun controllo di integrità dei dati è visibile. Pertanto, il contenuto di un cookie che viene letto da questo metodo può essere attaccato dall'utente che ha ricevuto o da qualsiasi utente malintenzionato ha ottenuto il valore di cookie crittografato.

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

## <a name="example-code-following-recommended-practices---managed"></a>Esempio di codice di esempio consigliate - gestiti

Esempio di codice seguente viene utilizzato un formato del messaggio non standard

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

in cui il `cipher_algorithm_id` e `hmac_algorithm_id` identificatori di algoritmi sono locali dell'applicazione (standard) rappresentazioni di tali algoritmi. Questi identificatori possono risultare utile in altre parti del protocollo di messaggistica esistente anziché come un bare bytestream concatenati.

Questo esempio Usa anche una sola chiave master per derivare una chiave di crittografia sia una chiave HMAC. Viene fornito sia per maggiore praticità per l'attivazione di un'applicazione singolarmente codificati in un'applicazione con chiave basata sul doppio e incoraggiare mantenendo i valori come diversi le due chiavi. Garantisce inoltre che la chiave HMAC e chiave di crittografia non perdano la sincronizzazione.

In questo esempio non accetta un <xref:System.IO.Stream> per la crittografia o decrittografia. L'imposta come corrente dei dati formato un passaggio crittografare difficile perché la `hmac_tag` valore precede il testo crittografato. Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi a dimensione fissa all'inizio di mantenere più semplice il parser. Con questo formato di dati, un passaggio decrypt è possibile, anche se un responsabile dell'implementazione viene avvisati da chiamare GetHashAndReset e verificare i risultati prima di chiamare TransformFinalBlock. Se la crittografia di streaming è importante, una modalità diversa AE potrebbe essere necessario.

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
