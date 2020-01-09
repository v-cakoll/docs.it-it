---
title: Vulnerabilità della decrittografia CBC
description: Informazioni su come rilevare e attenuare le vulnerabilità temporali con la decrittografia simmetrica della modalità CBC (Cipher-Block-Chaining) usando la spaziatura interna.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 87f8e3c53e4d06f6a4edc7670891ac83ec8d65ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705847"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>Vulnerabilità di temporizzazione con decrittografia simmetrica modalità CBC usando il riempimento

Microsoft ritiene che non sia più sicuro decrittografare i dati crittografati con la modalità CBC (Cipher-Block-Chaining) della crittografia simmetrica quando è stata applicata la spaziatura verificabile senza prima verificare l'integrità del testo crittografato, ad eccezione di quelli specifici circostanze. Questo giudizio è basato sulla ricerca crittografica attualmente nota. 

## <a name="introduction"></a>Introduzione

Un attacco Oracle di riempimento è un tipo di attacco contro i dati crittografati che consente all'autore dell'attacco di decrittografare il contenuto dei dati, senza conoscere la chiave.

Un Oracle si riferisce a "Tell", che fornisce a un utente malintenzionato informazioni sull'eventuale correttezza dell'azione che sta eseguendo. Immaginate di giocare una lavagna o un gioco di carte con un figlio. Quando il suo volto è illuminato da un grande sorriso perché pensa di avere un ottimo spostamento, si tratta di un Oracle. L'utente, come avversario, può utilizzare questo Oracle per pianificare il prossimo spostamento in modo appropriato.

La spaziatura interna è un termine di crittografia specifico. Alcune crittografie, ovvero gli algoritmi usati per crittografare i dati, funzionano su blocchi di dati in cui ogni blocco è a dimensione fissa. Se i dati che si desidera crittografare non sono di dimensioni corrette per riempire i blocchi, i dati vengono riempiti fino a quando non vengono completati. Molte forme di riempimento richiedono che la spaziatura interna sia sempre presente, anche se l'input originale ha dimensioni corrette. Ciò consente di rimuovere sempre la spaziatura interna in modo sicuro al momento della decrittografia.

Unendo i due elementi, un'implementazione del software con un Oracle di riempimento rivela se i dati decrittografati hanno un riempimento valido. Oracle potrebbe essere semplice come restituire un valore che indica "riempimento non valido" o qualcosa di più complicato, ad esempio per l'elaborazione di un blocco valido anziché un blocco non valido.

Le crittografie basate su blocchi hanno un'altra proprietà, denominata mode, che determina la relazione tra i dati nel primo blocco e i dati nel secondo blocco e così via. Una delle modalità più diffuse è CBC. CBC introduce un blocco iniziale casuale, noto come vettore di inizializzazione (IV), e combina il blocco precedente con il risultato della crittografia statica per fare in modo che la crittografia dello stesso messaggio con la stessa chiave non produca sempre lo stesso output crittografato.

Un utente malintenzionato può utilizzare una spaziatura interna Oracle, in combinazione con il modo in cui i dati CBC sono strutturati, per inviare messaggi leggermente modificati al codice che espone Oracle e per restare in attesa dell'invio dei dati fino a quando Oracle non indica che i dati sono corretti. Da questa risposta, l'autore dell'attacco può decrittografare il byte del messaggio per byte.

Le reti di computer moderne hanno una qualità elevata che un utente malintenzionato può rilevare le differenze minime (meno di 0,1 ms) nel tempo di esecuzione nei sistemi remoti. Le applicazioni che presuppongono una corretta decrittografia possono verificarsi solo quando i dati non sono stati manomessi possono essere vulnerabili ad attacchi da strumenti progettati per osservare le differenze di decrittografia con esito positivo e negativo. Questa differenza di tempo può essere più significativa in alcune lingue o librerie rispetto ad altre, ora si ritiene che si tratti di una minaccia pratica per tutte le lingue e le librerie quando viene presa in considerazione la risposta dell'applicazione a un errore.

Questo attacco si basa sulla possibilità di modificare i dati crittografati e di testare il risultato con Oracle. L'unico modo per attenuare completamente l'attacco consiste nel rilevare le modifiche apportate ai dati crittografati e rifiutare di eseguire azioni su di essa. Il modo standard per eseguire questa operazione consiste nel creare una firma per i dati e convalidare tale firma prima di eseguire qualsiasi operazione. La firma deve essere verificabile, non può essere creata dall'utente malintenzionato. in caso contrario, modifica i dati crittografati, quindi calcola una nuova firma in base ai dati modificati. Un tipo comune di firma appropriata è noto come codice HMAC (chiave-hash Message Authentication Code). Un HMAC differisce da un checksum in quanto accetta una chiave privata, nota solo alla persona che produce l'HMAC e alla persona che la convalida. Senza il possesso della chiave, non è possibile produrre un HMAC corretto. Quando si ricevono i dati, si accettano i dati crittografati, si calcola in modo indipendente il HMAC usando la chiave privata e la condivisione del mittente, quindi si confronta il HMAC inviato rispetto a quello calcolato. Questo confronto deve essere un tempo costante, in caso contrario è stato aggiunto un altro Oracle rilevabile, che consente un tipo diverso di attacco.

In sintesi, per utilizzare le crittografie a blocchi con CBC in modo sicuro, è necessario combinarle con un HMAC (o un altro controllo di integrità dei dati) convalidato utilizzando un confronto temporale costante prima di tentare di decrittografare i dati. Poiché tutti i messaggi modificati hanno la stessa quantità di tempo per produrre una risposta, l'attacco viene impedito.

## <a name="who-is-vulnerable"></a>Utenti vulnerabili

Questa vulnerabilità è valida per le applicazioni gestite e native che eseguono la crittografia e la decrittografia. Sono inclusi, ad esempio:

- Applicazione che esegue la crittografia di un cookie per la decrittografia successiva nel server.
- Un'applicazione di database che consente agli utenti di inserire dati in una tabella le cui colonne vengono decrittografate in un secondo momento.
- Applicazione per il trasferimento dei dati basata sulla crittografia mediante una chiave condivisa per proteggere i dati in transito.
- Applicazione che esegue la crittografia e la decrittografia dei messaggi "all'interno" del tunnel TLS.

Si noti che l'uso di TLS autonomo potrebbe non essere protetto in questi scenari.

Applicazione vulnerabile:

- Decrittografa i dati utilizzando la modalità di crittografia CBC con una modalità di riempimento verificabile, ad esempio PKCS # 7 o ANSI X. 923.
- Esegue la decrittografia senza avere eseguito un controllo di integrità dei dati (tramite un MAC o una firma digitale asimmetrica).

Questo vale anche per le applicazioni basate su astrazioni rispetto a quelle primitive, ad esempio la struttura EnvelopedData della sintassi del messaggio crittografico (PKCS # 7/CMS).

## <a name="related-areas-of-concern"></a>Aree problematiche correlate

La ricerca ha indotto Microsoft a preoccuparsi dei messaggi CBC riempiti con riempimento ISO 10126 equivalente quando il messaggio presenta una struttura di piè di pagina nota o prevedibile. Ad esempio, contenuto preparato secondo le regole del W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml). Sebbene il materiale sussidiario W3C per firmare il messaggio e quindi crittografato sia stato considerato appropriato al momento, Microsoft ora consiglia di eseguire sempre la crittografia-then-sign.

Gli sviluppatori di applicazioni devono essere sempre consapevoli di verificare l'applicabilità di una chiave di firma asimmetrica, in quanto non esiste alcuna relazione di trust intrinseca tra una chiave asimmetrica e un messaggio arbitrario.

## <a name="details"></a>Dettagli

Storicamente, è stato concordato che è importante sia crittografare che autenticare i dati importanti, usando mezzi quali le firme HMAC o RSA. Tuttavia, sono state apportate indicazioni meno chiare su come sequenziare le operazioni di crittografia e autenticazione. A causa della vulnerabilità descritta in questo articolo, le linee guida di Microsoft ora utilizzano sempre il paradigma "crittografia-firma". Per prima cosa, crittografare i dati usando una chiave simmetrica, quindi calcolare un MAC o una firma asimmetrica sul testo crittografato (dati crittografati). Per la decrittografia dei dati, eseguire il contrario. Prima di tutto, confermare il MAC o la firma del testo crittografato, quindi decrittografarlo.

Una classe di vulnerabilità nota come "attacchi Oracle di riempimento" è nota per più di 10 anni. Queste vulnerabilità consentono a un utente malintenzionato di decrittografare i dati crittografati da algoritmi di blocco simmetrico, ad esempio AES e 3DES, usando non più di 4096 tentativi per blocco di dati. Queste vulnerabilità utilizzano il fatto che le crittografie a blocchi vengono utilizzate più di frequente con i dati di riempimento verificabili alla fine. È stato rilevato che se un utente malintenzionato può manomettere il testo crittografato e verificare se la manomissione ha causato un errore nel formato del riempimento alla fine, l'autore dell'attacco può decrittografare i dati.

Inizialmente gli attacchi pratici si basavano su servizi che restituivano codici di errore diversi a seconda che il riempimento fosse valido, ad esempio la vulnerabilità ASP.NET [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070). Microsoft ora ritiene tuttavia che sia pratica eseguire attacchi simili utilizzando solo le differenze di tempo tra l'elaborazione di spazi di riempimento validi e non validi.

Se lo schema di crittografia usa una firma e la verifica della firma viene eseguita con un runtime fisso per una data lunghezza dei dati (indipendentemente dal contenuto), l'integrità dei dati può essere verificata senza emettere informazioni a un utente malintenzionato tramite un [canale laterale](https://en.wikipedia.org/wiki/Side-channel_attack). Poiché il controllo di integrità rifiuta tutti i messaggi manomessi, la minaccia Oracle di riempimento viene mitigata.

## <a name="guidance"></a>Informazioni aggiuntive

Prima di tutto, Microsoft consiglia che tutti i dati con riservatezza devono essere trasmessi tramite Transport Layer Security (TLS), il successore di Secure Sockets Layer (SSL).

Analizzare quindi l'applicazione per:

- Comprendere con precisione la crittografia che si sta eseguendo e la crittografia fornita dalle piattaforme e dalle API in uso.
- Accertarsi che ogni utilizzo a ogni livello di un algoritmo di crittografia a [blocchi](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)simmetrico, ad esempio AES e 3DES, in modalità CBC includa l'uso di un controllo di integrità dei dati con chiave segreta (una firma asimmetrica, un HMAC o la modalità di crittografia in una modalità di [crittografia autenticata](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE), ad esempio GCM o CCM.

In base alla ricerca corrente, in genere si ritiene che, quando i passaggi di autenticazione e di crittografia vengono eseguiti in modo indipendente per le modalità di crittografia non AE, l'autenticazione del testo crittografato (Encrypt-then-sign) è la migliore opzione generale. Tuttavia, non esiste alcuna risposta corretta per la crittografia e questa generalizzazione non è altrettanto valida come consigli diretti da un crittografista professionale.

Le applicazioni che non sono in grado di modificare il formato di messaggistica ma eseguono la decrittografia CBC non autenticata sono incoraggiate a provare a incorporare le mitigazioni, ad esempio:

- Decrittografare senza consentire al Decryptor di verificare o rimuovere la spaziatura interna:
  - È necessario rimuovere o ignorare qualsiasi riempimento applicato, che verrà spostato nell'applicazione.
  - Il vantaggio è che la verifica e la rimozione della spaziatura interna possono essere incorporate in altre logiche di verifica dei dati delle applicazioni. Se la verifica della spaziatura interna e la verifica dei dati possono essere eseguite in un tempo costante, la minaccia viene ridotta.
  - Poiché l'interpretazione del riempimento modifica la lunghezza del messaggio percepito, è possibile che siano ancora presenti informazioni sui tempi emesse da questo approccio.
- Modificare la modalità di riempimento decrittografia in ISO10126:
  - Il riempimento della decrittografia ISO10126 è compatibile con la spaziatura interna della crittografia PKCS7 e la spaziatura con crittografia ANSIX923.
  - Se si modifica la modalità, le informazioni Oracle di riempimento vengono ridotte a 1 byte anziché all'intero blocco. Tuttavia, se il contenuto dispone di un piè di pagina noto, ad esempio un elemento XML di chiusura, gli attacchi correlati possono continuare ad attaccare il resto del messaggio.
  - Questo non impedisce inoltre il ripristino in testo non crittografato nelle situazioni in cui l'autore dell'attacco può assegnare lo stesso testo normale crittografato più volte con un offset del messaggio diverso.
- Controllare la valutazione di una chiamata di decrittografia per smorzare il segnale di temporizzazione:
  - Il calcolo del tempo di attesa deve avere un valore minimo superiore alla quantità massima di tempo che l'operazione di decrittografia richiederebbe per qualsiasi segmento di dati che contiene spaziatura interna.
  - I calcoli temporali devono essere eseguiti in base alle linee guida per l' [acquisizione di timestamp ad alta risoluzione](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), non usando <xref:System.Environment.TickCount?displayProperty=nameWithType> (soggetto a capovolgimento/overflow) o sottraendo due timestamp di sistema (soggetto a errori di regolazione NTP).
  - I calcoli temporali devono essere inclusi nell'operazione di decrittografia, incluse tutte le potenziali eccezioni C++ nelle applicazioni gestite o, non solo per la fine.
  - Se l'esito positivo o negativo è stato ancora determinato, il Gate di temporizzazione deve restituire un errore alla scadenza.
- I servizi che eseguono la decrittografia non autenticata devono avere il monitoraggio per rilevare che è stato raggiunto un diluvio di messaggi "non validi".
  - Tenere presente che questo segnale contiene sia falsi positivi (dati legittimamente danneggiati) che falsi negativi (diffondendo l'attacco in un tempo sufficientemente lungo per eludere il rilevamento).

## <a name="finding-vulnerable-code---native-applications"></a>Individuazione di applicazioni native del codice vulnerabili

Per i programmi compilati con la libreria di crittografia di Windows: Next Generation (CNG):

- La chiamata di decrittografia è [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specificando il flag `BCRYPT_BLOCK_PADDING`.
- L'handle di chiave è stato inizializzato chiamando [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) con [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) impostato su `BCRYPT_CHAIN_MODE_CBC`.
  - Poiché `BCRYPT_CHAIN_MODE_CBC` è l'impostazione predefinita, il codice interessato potrebbe non avere assegnato alcun valore per `BCRYPT_CHAINING_MODE`.

Per i programmi compilati con l'API di crittografia Windows precedente:

- La chiamata di decrittografia è [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) con `Final=TRUE`.
- L'handle di chiave è stato inizializzato chiamando [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) con [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) impostato su `CRYPT_MODE_CBC`.
  - Poiché `CRYPT_MODE_CBC` è l'impostazione predefinita, il codice interessato potrebbe non avere assegnato alcun valore per `KP_MODE`.

## <a name="finding-vulnerable-code---managed-applications"></a>Individuazione di applicazioni gestite dal codice vulnerabili

- La chiamata di decrittografia è relativa ai metodi <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> o <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> in <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.
  - Sono inclusi i seguenti tipi derivati all'interno di .NET, ma possono includere anche tipi di terze parti:
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
- La proprietà <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>o <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.
  - Poiché <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> è l'impostazione predefinita, il codice interessato potrebbe non avere mai assegnato la proprietà <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType>.
- La proprietà <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> è stata impostata su <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - Poiché <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> è l'impostazione predefinita, il codice interessato potrebbe non avere mai assegnato la proprietà <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType>.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>Ricerca del codice vulnerabile sintassi del messaggio crittografico

Un messaggio EnvelopedData CMS non autenticato il cui contenuto crittografato usa la modalità CBC di AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) o RC2 (1.2.840.113549.3.2) vulnerabile, oltre ai messaggi che utilizzano altri algoritmi di crittografia a blocchi in modalità CBC.

Sebbene le crittografie di flusso non siano soggette a questa particolare vulnerabilità, Microsoft consiglia sempre di autenticare i dati controllando il valore di ContentEncryptionAlgorithm.

Per le applicazioni gestite, un BLOB EnvelopedData CMS può essere rilevato come qualsiasi valore passato a <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.

Per le applicazioni native, è possibile rilevare un BLOB EnvelopedData CMS come qualsiasi valore fornito a un handle CMS tramite [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) il cui [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) risultante è `CMSG_ENVELOPED` e/o l'handle del CMS viene inviato in un secondo momento `CMSG_CTRL_DECRYPT` istruzione tramite [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).

## <a name="vulnerable-code-example---managed"></a>Esempio di codice vulnerabile-gestito

Questo metodo legge un cookie e lo decrittografa e non è visibile alcun controllo di integrità dei dati. Il contenuto di un cookie letto da questo metodo può pertanto essere attaccato dall'utente che lo ha ricevuto o da qualsiasi utente malintenzionato che ha ottenuto il valore del cookie crittografato.

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

## <a name="example-code-following-recommended-practices---managed"></a>Codice di esempio che segue le procedure consigliate-gestito

Il codice di esempio seguente usa un formato di messaggio non standard

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

dove gli identificatori dell'algoritmo `cipher_algorithm_id` e `hmac_algorithm_id` sono rappresentazioni locali dell'applicazione (non standard) di questi algoritmi. Questi identificatori possono avere senso in altre parti del protocollo di messaggistica esistente, anziché come ByteStream concatenato bare.

Questo esempio usa anche una singola chiave master per derivare una chiave di crittografia e una chiave HMAC. Questa operazione viene fornita sia per praticità per trasformare un'applicazione con chiave singola in un'applicazione a doppia chiave che per favorire la conservazione delle due chiavi come valori diversi. Garantisce inoltre che la chiave HMAC e la chiave di crittografia non possano uscire dalla sincronizzazione.

Questo esempio non accetta un <xref:System.IO.Stream> per la crittografia o la decrittografia. Il formato dati corrente semplifica la crittografia di un passaggio, perché il valore `hmac_tag` precede il testo crittografato. Tuttavia, questo formato è stato scelto perché mantiene tutti gli elementi a dimensione fissa all'inizio per mantenere più semplice il parser. Con questo formato di dati, è possibile decrittografare un passaggio, anche se un implementatore viene avvertito per chiamare GetHashAndReset e verificare il risultato prima di chiamare TransformFinalBlock. Se la crittografia del flusso è importante, potrebbe essere necessaria una modalità AE diversa.

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
