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
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento

Microsoft ritiene che non sia più sicuro decrittografare i dati crittografati con la modalità Cipher-Block-Chaining (CBC) di crittografia simmetrica quando è stata applicata una spaziatura interna verificabile senza prima garantire l'integrità del testo crittografato, ad eccezione di Circostanze. Questo giudizio si basa su ricerche crittografiche attualmente note.

## <a name="introduction"></a>Introduzione

Un attacco oracolo imbottitura è un tipo di attacco contro i dati crittografati che consente all'utente malintenzionato di decrittografare il contenuto dei dati, senza conoscere la chiave.

Un oracolo si riferisce a un "racconto" che fornisce a un utente malintenzionato informazioni sul fatto che l'azione che sta eseguendo sia corretta o meno. Immagina di giocare a un gioco da tavolo o a carte con un bambino. Quando il loro viso si illumina con un grande sorriso perché pensano di fare una buona mossa, è un oracolo. Tu, come avversario, puoi usare questo oracolo per pianificare la tua prossima mossa in modo appropriato.

Padding è un termine crittografico specifico. Alcuni cifrari, che sono gli algoritmi utilizzati per crittografare i dati, funzionano su blocchi di dati in cui ogni blocco è di dimensioni fisse. Se i dati che si desidera crittografare non sono la dimensione corretta per riempire i blocchi, i dati vengono riempiti fino a quando non lo fa. Molte forme di riempimento richiedono che la spaziatura interna sia sempre presente, anche se l'input originale era della dimensione corretta. Ciò consente di rimuovere sempre l'imbottitura in modo sicuro al momento della decrittografia.

Mettendo insieme le due cose, un'implementazione software con un oracolo imbottitura rivela se i dati decrittografati hanno una spaziatura interna valida. L'oracolo potrebbe essere qualcosa di semplice come la restituzione di un valore che dice "padding non valido" o qualcosa di più complicato come prendere un tempo misurabilmente diverso per elaborare un blocco valido al contrario di un blocco non valido.

Le crittografie basate su blocchi hanno un'altra proprietà, denominata modalità, che determina la relazione dei dati nel primo blocco con i dati nel secondo blocco e così via. Una delle modalità più comunemente utilizzate è CBC. CBC introduce un blocco casuale iniziale, noto come vettore di inizializzazione (IV), e combina il blocco precedente con il risultato della crittografia statica per rendere tale che la crittografia dello stesso messaggio con la stessa chiave non produca sempre lo stesso output crittografato.

Un utente malintenzionato può utilizzare un oracolo di spaziatura interna, in combinazione con il modo in cui sono strutturati i dati CBC, per inviare messaggi leggermente modificati al codice che espone l'oracolo e continuare a inviare dati fino a quando l'oracolo non indica che i dati sono corretti. Da questa risposta, l'utente malintenzionato può decrittografare il byte del messaggio per byte.

Le reti di computer moderne sono di qualità così elevata che un utente malintenzionato può rilevare differenze molto piccole (meno di 0,1 ms) nel tempo di esecuzione sui sistemi remoti.Le applicazioni che assumono che una decrittografia di successo può verificarsi solo quando i dati non è stato manomesso potrebbe essere vulnerabile agli attacchi da strumenti che sono progettati per osservare le differenze nella decrittografia riuscita e non riuscita. Anche se questa differenza di temporizzazione può essere più significativa in alcuni linguaggi o librerie rispetto ad altri, si ritiene ora che questa sia una minaccia pratica per tutti i linguaggi e le librerie quando viene presa in considerazione la risposta dell'applicazione all'errore.

Questo attacco si basa sulla possibilità di modificare i dati crittografati e testare il risultato con l'oracolo. L'unico modo per mitigare completamente l'attacco è quello di rilevare le modifiche ai dati crittografati e rifiutare di eseguire qualsiasi azione su di esso. Il modo standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima che vengano eseguite le operazioni. La firma deve essere verificabile, non può essere creata dall'utente malintenzionato, altrimenti modificherebbe i dati crittografati, quindi calcola una nuova firma in base ai dati modificati. Un tipo comune di firma appropriata è noto come codice HMAC (Keyed-Hash Message Authentication Code). Un HMAC differisce da un checksum in quanto richiede una chiave segreta, nota solo alla persona che produce l'HMAC e alla persona che la convalida. Senza il possesso della chiave, non è possibile produrre un HMAC corretto. Quando si ricevono i dati, è necessario prendere i dati crittografati, calcolare in modo indipendente l'HMAC utilizzando la chiave segreta che tu e il mittente condividete, quindi confrontare l'HMAC inviato con quello calcolato. Questo confronto deve essere un tempo costante, altrimenti hai aggiunto un altro oracolo rilevabile, consentendo un diverso tipo di attacco.

In sintesi, per utilizzare i cifrari a blocchi CBC imbottiti in modo sicuro, è necessario combinarli con un HMAC (o un altro controllo di integrità dei dati) convalidato utilizzando un confronto temporale costante prima di tentare di decrittografare i dati. Poiché tutti i messaggi alterati richiedono la stessa quantità di tempo per produrre una risposta, l'attacco viene impedito.

## <a name="who-is-vulnerable"></a>Chi è vulnerabile

Questa vulnerabilità si applica sia alle applicazioni gestite che native che eseguono la propria crittografia e decrittografia. Ciò include, ad esempio:

- Applicazione che crittografa un cookie per la decrittografia successiva sul server.
- Applicazione di database che consente agli utenti di inserire dati in una tabella le cui colonne vengono successivamente decrittografate.
- Un'applicazione di trasferimento dati che si basa sulla crittografia utilizzando una chiave condivisa per proteggere i dati in transito.
- Un'applicazione che crittografa e decrittografa i messaggi "all'interno" del tunnel TLS.

Tieni presente che l'utilizzo di TLS da solo potrebbe non proteggere l'utente in questi scenari.

Un'applicazione vulnerabile:

- Decrittografa i dati utilizzando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio PKCS-7 o ANSI X.923.
- Esegue la decrittografia senza aver eseguito un controllo di integrità dei dati (tramite un MAC o una firma digitale asimmetrica).

Questo vale anche per le applicazioni basate sulle astrazioni sopra queste primitive, ad esempio la struttura EnvelopedData della sintassi dei messaggi di crittografia (PKCS/7/CMS).

## <a name="related-areas-of-concern"></a>Aree di interesse correlate

La ricerca ha portato Microsoft a essere ulteriormente preoccupato per i messaggi CBC che sono imbottiti con spaziatura interna equivalente ISO 10126 quando il messaggio ha una struttura di piè di pagina nota o prevedibile. Ad esempio, il contenuto preparato in base alle regole del W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml). Mentre le linee guida W3C per firmare il messaggio quindi crittografare è stato considerato appropriato al momento, Microsoft ora consiglia di eseguire sempre crittografia-poi-firma.

Gli sviluppatori di applicazioni devono sempre tenere presente l'applicabilità di una chiave di firma asimmetrica, in quanto non esiste alcuna relazione di trust intrinseca tra una chiave asimmetrica e un messaggio arbitrario.

## <a name="details"></a>Dettagli

Storicamente, c'è stato consenso sul fatto che sia importante crittografare e autenticare i dati importanti, utilizzando mezzi come le firme HMAC o RSA. Tuttavia, sono state fornite indicazioni meno chiare su come sequenziare le operazioni di crittografia e autenticazione. A causa della vulnerabilità descritta in questo articolo, la guida di Microsoft è ora di utilizzare sempre il paradigma "crittografa-allora-firma". Ovvero, prima crittografare i dati utilizzando una chiave simmetrica, quindi calcolare una firma MAC o asimmetrica sul testo crittografato (dati crittografati). Quando si decrittografano i dati, eseguire l'inverso. In primo luogo, confermare il MAC o la firma del testo cifrato, quindi decrittografarlo.

Una classe di vulnerabilità note come "attacchi oracolo imbottitura" sono stati conosciuti per esistere per oltre 10 anni. Queste vulnerabilità consentono a un utente malintenzionato di decrittografare i dati crittografati da algoritmi a blocchi simmetrici, ad esempio AES e 3DES, utilizzando non più di 4096 tentativi per blocco di dati. Queste vulnerabilità fanno uso del fatto che i cifrari a blocchi sono più frequentemente utilizzati con i dati di riempimento verificabili alla fine. Si è scoperto che se un utente malintenzionato può manomettere il testo crittografato e scoprire se la manomissione ha causato un errore nel formato della spaziatura interna alla fine, l'utente malintenzionato può decrittografare i dati.

Inizialmente, gli attacchi pratici erano basati su servizi che restituivano codici di errore diversi a seconda che la spaziatura interna fosse valida, ad esempio la vulnerabilità ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Tuttavia, Microsoft ritiene ora che sia pratico condurre attacchi simili utilizzando solo le differenze di tempo tra l'elaborazione di riempimento valido e non valido.

A condizione che lo schema di crittografia impieghi una firma e che la verifica della firma venga eseguita con un runtime fisso per una determinata lunghezza di dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza emettere alcuna informazione a un utente malintenzionato tramite un [canale laterale.](https://en.wikipedia.org/wiki/Side-channel_attack) Poiché il controllo di integrità rifiuta tutti i messaggi manomessi, la minaccia dell'oracolo della spaziatura interna viene attenuata.

## <a name="guidance"></a>Materiale sussidiario

In primo luogo, Microsoft consiglia di trasmettere tutti i dati con necessità di riservatezza tramite Transport Layer Security (TLS), il successore di Secure Sockets Layer (SSL).

Successivamente, analizzare l'applicazione per:Next, analyze your application to:

- Comprendere con precisione quale crittografia si sta eseguendo e quale crittografia viene fornita dalle piattaforme e API in uso.
- Assicurarsi che ogni utilizzo a ogni livello di un algoritmo di crittografia a [blocchi simmetrico,](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)ad esempio AES e 3DES, in modalità CBC incorpori l'utilizzo di un controllo di integrità dei dati con chiave segreta (una firma asimmetrica, un HMAC o per modificare la modalità di crittografia in una modalità di [crittografia autenticata](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE), ad esempio GCM o CCM.

Sulla base della ricerca corrente, è generalmente creduto che quando i passaggi di autenticazione e crittografia vengono eseguiti in modo indipendente per le modalità di crittografia non AE, l'autenticazione del testo crittografato (crittografia-poi-firma) è la migliore opzione generale. Tuttavia, non c'è nessuna risposta corretta per tutti e questa generalizzazione non è buona come la consulenza diretta di un crittografo professionista.

Le applicazioni che non sono in grado di modificare il formato di messaggistica ma eseguono la decrittografia CBC non autenticata sono incoraggiate a provare a incorporare attenuazioni come:

- Decrittografare senza consentire al decryptor di verificare o rimuovere la spaziatura interna:
  - Qualsiasi riempimento che è stato applicato deve ancora essere rimosso o ignorato, si sta spostando il carico nell'applicazione.
  - Il vantaggio è che la verifica e la rimozione della spaziatura interna possono essere incorporate in altre logiche di verifica dei dati dell'applicazione. Se la verifica dell'imbottitura e la verifica dei dati possono essere eseguite in tempi costanti, la minaccia viene ridotta.
  - Poiché l'interpretazione della spaziatura interna modifica la lunghezza del messaggio percepito, potrebbero essere ancora presenti informazioni di temporizzazione generate da questo approccio.
- Modificare la modalità di decrittografia padding in ISO10126:
  - La spaziatura interna di decrittografia ISO10126 è compatibile sia con la spaziatura interna di crittografia PKCS7 che con la spaziatura interna di crittografia ANSIX923.
  - La modifica della modalità riduce la conoscenza dell'oracolo di riempimento a 1 byte anziché l'intero blocco. Tuttavia, se il contenuto ha un piè di pagina noto, ad esempio un elemento XML di chiusura, gli attacchi correlati possono continuare ad attaccare il resto del messaggio.
  - In questo modo non viene inoltre impedito il ripristino in testo normale in situazioni in cui l'utente malintenzionato può coemettere lo stesso testo in chiaro da crittografare più volte con un offset del messaggio diverso.
- Gate la valutazione di una chiamata di decrittazione per smorzare il segnale di temporizzazione:
  - Il calcolo del tempo di conservazione deve avere un valore minimo superiore alla quantità massima di tempo necessaria per l'operazione di decrittografia per qualsiasi segmento di dati che contiene spaziatura interna.
  - I calcoli temporali devono essere eseguiti in base alle indicazioni fornite <xref:System.Environment.TickCount?displayProperty=nameWithType> in Acquisizione di timestamp ad alta [risoluzione,](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)non utilizzando (soggetto a rollover/overflow) o sottraendo due timestamp di sistema (soggetto a errori di regolazione NTP).
  - I calcoli temporali devono includere l'operazione di decrittografia, incluse tutte le potenziali eccezioni nelle applicazioni gestite o in C, non solo riempite alla fine.
  - Se l'esito positivo o negativo è stato determinato ancora, il gate di temporizzazione deve restituire l'errore alla scadenza.
- I servizi che eseguono la decrittografia non autenticata devono disporre di un monitoraggio per rilevare che è arrivata una marea di messaggi "non validi".
  - Tenete a mente che questo segnale trasporta sia falsi positivi (dati legittimamente corrotti) e falsi negativi (diffondendo l'attacco in un tempo sufficientemente lungo per eludere il rilevamento).

## <a name="finding-vulnerable-code---native-applications"></a>Ricerca di codice vulnerabile - applicazioni nativeFinding vulnerable code - native applications

Per i programmi creati in base alla libreria CNG (Windows Cryptography: Next Generation):

- La chiamata di decrittografia è a [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specificando il `BCRYPT_BLOCK_PADDING` flag.
- L'handle di chiave è stato inizializzato [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) chiamando `BCRYPT_CHAIN_MODE_CBC` [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con BCRYPT_CHAINING_MODE impostato su .
  - Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, il `BCRYPT_CHAINING_MODE`codice interessato potrebbe non avere assegnato alcun valore per .

Per i programmi creati in base alla precedente API di crittografia di Windows:

- La chiamata di decrittografia è `Final=TRUE`a [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con .
- L'handle di chiave è stato inizializzato [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) chiamando `CRYPT_MODE_CBC` [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con KP_MODE impostato su .
  - Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, il `KP_MODE`codice interessato potrebbe non avere assegnato alcun valore per .

## <a name="finding-vulnerable-code---managed-applications"></a>Ricerca di codice vulnerabile - applicazioni gestiteFinding vulnerable code - managed applications

- La chiamata di decrittografia <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> è <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>ai metodi o su .
  - Sono inclusi i seguenti tipi derivati all'interno di .NET, ma possono anche includere tipi di terze parti:
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
- La <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> proprietà è <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>stata <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>impostata su , , o .
  - Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> il codice interessato potrebbe non aver mai assegnato la proprietà.
- La <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> proprietà è stata impostata su<xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> il codice interessato potrebbe non aver mai assegnato la proprietà.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Ricerca di codice vulnerabile - sintassi dei messaggi crittograficiFinding vulnerable code - cryptographic message syntax

Un messaggio CMS EnvelopedData non autenticato il cui contenuto crittografato utilizza la modalità CBC di AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) è vulnerabili, così come i messaggi che utilizzano qualsiasi altro algoritmo di crittografia a blocchi in modalità CBC.

Sebbene le crittografie di flusso non siano soggette a questa particolare vulnerabilità, Microsoft consiglia di autenticare sempre i dati durante l'ispezione del valore ContentEncryptionAlgorithm.

Per le applicazioni gestite, un BLOB CMS EnvelopedData <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>può essere rilevato come qualsiasi valore passato a .

Per le applicazioni native, un BLOB CMS EnvelopedData può essere rilevato come qualsiasi valore `CMSG_ENVELOPED` fornito a un handle CMS `CMSG_CTRL_DECRYPT` tramite [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) il cui [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) risultante è e/o l'handle CMS viene successivamente inviato un'istruzione tramite [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Esempio di codice vulnerabile - gestitoVulnerable code example - managed

Questo metodo legge un cookie e lo decrittografa e non è visibile alcun controllo dell'integrità dei dati. Pertanto, il contenuto di un cookie letto da questo metodo può essere attaccato dall'utente che lo ha ricevuto o da qualsiasi utente malintenzionato che ha ottenuto il valore del cookie crittografato.

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

## <a name="example-code-following-recommended-practices---managed"></a>Codice di esempio che segue le procedure consigliate : gestito

Il codice di esempio seguente usa un formato di messaggio non standard

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

dove `cipher_algorithm_id` gli `hmac_algorithm_id` identificatori e gli identificatori di algoritmo sono rappresentazioni locali dell'applicazione (non standard) di tali algoritmi. Questi identificatori possono avere senso in altre parti del protocollo di messaggistica esistente anziché come un flusso di byte concatenato a livello bare.

In questo esempio viene inoltre utilizzata una singola chiave master per derivare sia una chiave di crittografia che una chiave HMAC. Questo viene fornito sia per comodità per trasformare un'applicazione con chiave in modo singly in un'applicazione dual-keyed, sia per incoraggiare a mantenere le due chiavi come valori diversi. Garantisce inoltre che la chiave HMAC e la chiave di crittografia non possano uscire dalla sincronizzazione.

In questo esempio non <xref:System.IO.Stream> viene accettato un per la crittografia o la decrittografia. Il formato dati corrente rende difficile `hmac_tag` la crittografia a un passaggio perché il valore precede il testo crittografato. Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi di dimensioni fisse all'inizio per mantenere il parser più semplice. Con questo formato di dati, è possibile la decrittografia un passaggio, anche se un implementatore viene avvertito di chiamare GetHashAndReset e verificare il risultato prima di chiamare TransformFinalBlock.With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock. Se la crittografia di streaming è importante, potrebbe essere necessaria una modalità AE diversa.

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
