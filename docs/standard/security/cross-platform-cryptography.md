---
title: Crittografia multipiattaforma in .NET Core e .NET 5
description: Informazioni sulle funzionalità crittografiche sulle piattaforme supportate da .NET.
ms.date: 06/19/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography, cross-platform
- encryption, cross-platform
ms.openlocfilehash: 793a9bc55e5bd660374abd2ae81899e63ce3f36a
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85854014"
---
# <a name="cross-platform-cryptography-in-net-core-and-net-5"></a>Crittografia multipiattaforma in .NET Core e .NET 5

Le operazioni di crittografia in .NET Core e .NET 5 vengono eseguite dalle librerie del sistema operativo. Questa dipendenza presenta vantaggi:

* Le app .NET traggono vantaggio dall'affidabilità del sistema operativo. Mantenere le librerie di crittografia protette da vulnerabilità è una priorità elevata per i fornitori del sistema operativo. A tale scopo, forniscono gli aggiornamenti che devono essere applicati agli amministratori di sistema.
* Le app .NET possono accedere agli algoritmi convalidati FIPS se le librerie del sistema operativo sono convalidate da FIPS.

La dipendenza dalle librerie del sistema operativo significa anche che le app .NET possono usare solo le funzionalità crittografiche supportate dal sistema operativo. Anche se tutte le piattaforme supportano determinate funzionalità di base, alcune funzionalità supportate da .NET non possono essere usate in alcune piattaforme. Questo articolo identifica le funzionalità supportate in ogni piattaforma.

Questo articolo presuppone che l'utente abbia familiarità con la crittografia in .NET. Per ulteriori informazioni, vedere [modello di crittografia .NET](cryptography-model.md) e [servizi di crittografia .NET](cryptographic-services.md).

## <a name="hash-algorithms"></a>Algoritmi hash

Tutti gli algoritmi hash e le classi HMAC (hash-based Message Authentication), incluse le `*Managed` classi, rinviano alle librerie del sistema operativo. Sebbene le varie librerie del sistema operativo differiscano dalle prestazioni, devono essere compatibili.

## <a name="symmetric-encryption"></a>Crittografia simmetrica

Le crittografie e il concatenamento sottostanti vengono eseguiti dalle librerie di sistema e tutti sono supportati da tutte le piattaforme.

| Modalità di crittografia + | Windows | Linux | macOS |
|---------------|---------|-------|-------|
| AES-CBC       | ✔️     | ✔️    | ✔️   |
| AES-BCE       | ✔️     | ✔️    | ✔️   |
| 3DES-CBC      | ✔️     | ✔️    | ✔️   |
| 3DES-BCE      | ✔️     | ✔️    | ✔️   |
| DES-CBC       | ✔️     | ✔️    | ✔️   |
| DES-BCE       | ✔️     | ✔️    | ✔️   |

## <a name="authenticated-encryption"></a>Crittografia autenticata

Il supporto di crittografia autenticata (AE) viene fornito per AES-CCM e AES-GCM tramite le <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName> <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName> classi e.

In Windows e Linux, le implementazioni di AES-CCM e AES-GCM vengono fornite dalle librerie del sistema operativo.

### <a name="aes-ccm-and-aes-gcm-on-macos"></a>AES-CCM e AES-GCM in macOS

In macOS le librerie di sistema non supportano AES-CCM o AES-GCM per il codice di terze parti, pertanto le <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> classi e usano OpenSSL per il supporto. Gli utenti in macOS devono ottenere una copia appropriata di OpenSSL (libcrypto) per il funzionamento di questi tipi e devono trovarsi in un percorso da cui il sistema caricherà una libreria per impostazione predefinita. Si consiglia di installare OpenSSL da un gestore di pacchetti, ad esempio homebrew.

Le `libcrypto.0.9.7.dylib` `libcrypto.0.9.8.dylib` librerie e incluse in MacOS sono di versioni precedenti di OpenSSL e non verranno usate. Le `libcrypto.35.dylib` `libcrypto.41.dylib` librerie, e `libcrypto.42.dylib` sono da LibreSSL e non verranno usate.

### <a name="aes-ccm-keys-nonces-and-tags"></a>Chiavi AES-CCM, nonce e tag

* Dimensioni delle chiavi

  AES-CCM funziona con chiavi 128, 192 e 256 bit.

* Dimensioni nonce

  La <xref:System.Security.Cryptography.AesCcm> classe supporta 56, 64, 72, 80, 88, 96 e 104 bit (7, 8, 9, 10, 11, 12 e 13 byte) nonce.

* Dimensioni dei tag

  La <xref:System.Security.Cryptography.AesCcm> classe supporta la creazione o l'elaborazione di tag 32, 48, 64, 80, 96, 112 e 128 bit (4, 8, 10, 12, 14 e 16 byte).

### <a name="aes-gcm-keys-nonces-and-tags"></a>Chiavi AES-GCM, nonce e tag

* Dimensioni delle chiavi

  AES-GCM funziona con chiavi 128, 192 e 256 bit.

* Dimensioni nonce

  La <xref:System.Security.Cryptography.AesGcm> classe supporta solo nonce a 96 bit (12 byte).

* Dimensioni dei tag

  La <xref:System.Security.Cryptography.AesGcm> classe supporta la creazione o l'elaborazione di tag 96, 104, 112, 120 e 128 bit (12, 13, 14, 15 e 16 byte).

## <a name="asymmetric-cryptography"></a>Crittografia asimmetrica

In questa sezione sono incluse le sottosezioni seguenti:

* [RSA](#rsa)
* [ECDSA](#ecdsa)
* [ECDH](#ecdh)
* [DSA](#dsa)

### <a name="rsa"></a>RSA

La generazione di chiavi RSA (Rivest-Shamir-Adleman) viene eseguita dalle librerie del sistema operativo ed è soggetta alle limitazioni di dimensione e alle caratteristiche delle prestazioni.

Le operazioni della chiave RSA vengono eseguite dalle librerie del sistema operativo e i tipi di chiave che è possibile caricare sono soggetti ai requisiti del sistema operativo.

.NET non espone operazioni "Raw" (non riempite) di RSA.

Le librerie del sistema operativo vengono usate per la crittografia e la decrittografia. Non tutte le piattaforme supportano le stesse opzioni di riempimento:

| Modalità di riempimento                          | Windows (CNG) | Linux (OpenSSL) | macOS | Windows (CAPI) |
|---------------------------------------|---------------|-----------------|-------|----------------|
| Crittografia PKCS1                      | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-1                          | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-2 (SHA256, SHA384, SHA512) | ✔️           | ✔️              | ✔️   | ❌             |
| Firma PKCS1 (MD5, SHA-1)          | ✔️           | ✔️              | ✔️   | ✔️             |
| Firma di PKCS1 (SHA-2)               | ✔️           | ✔️              | ✔️   | ⚠️\*           |
| servizio supporto tecnico                                   | ✔️           | ✔️              | ✔️   | ❌             |

\*Windows CryptoAPI (CAPI) supporta la firma PKCS1 con un algoritmo SHA-2. Il singolo oggetto RSA, tuttavia, può essere caricato in un provider del servizio di crittografia (CSP) che non lo supporta.

#### <a name="rsa-on-windows"></a>RSA per Windows

* Windows CryptoAPI (CAPI) viene usato ogni volta che [`new RSACryptoServiceProvider()`](xref:System.Security.Cryptography.RSACryptoServiceProvider) viene usato.
* Viene utilizzata l'API Cryptography Next Generation (CNG) quando [`new RSACng()`](xref:System.Security.Cryptography.RSACng) si utilizza.
* L'oggetto restituito da <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> è alimentato internamente da Windows CNG. Questo utilizzo di Windows CNG è un dettaglio di implementazione ed è soggetto a modifiche.
* Il <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A> metodo di estensione per <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> restituisce un' <xref:System.Security.Cryptography.RSACng> istanza di. Questo utilizzo di <xref:System.Security.Cryptography.RSACng> è un dettaglio di implementazione ed è soggetto a modifiche.
* Il <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A> metodo di estensione per <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> preferisce attualmente un' <xref:System.Security.Cryptography.RSACng> istanza, ma se <xref:System.Security.Cryptography.RSACng> non è possibile aprire la chiave, verrà effettuato un <xref:System.Security.Cryptography.RSACryptoServiceProvider> tentativo. Il provider preferito è un dettaglio di implementazione ed è soggetto a modifiche.

#### <a name="rsa-native-interop"></a>Interoperabilità nativa RSA

.NET espone i tipi per consentire ai programmi di interagire con le librerie del sistema operativo utilizzate dal codice di crittografia .NET. I tipi necessari non vengono convertiti tra le piattaforme e devono essere usati direttamente solo quando necessario.

| Type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.RSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup>| ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.RSACng>                   | ✔️     | ❌            | ❌            |
| <xref:System.Security.Cryptography.RSAOpenSsl>               | ❌     | ✔️            | ⚠️<sup>2</sup> |

<sup>1</sup> in MacOS e Linux <xref:System.Security.Cryptography.RSACryptoServiceProvider> può essere usato per la compatibilità con i programmi esistenti. In tal caso, qualsiasi metodo che richiede l'interoperabilità del sistema operativo, ad esempio l'apertura di una chiave denominata, genera un'eccezione <xref:System.PlatformNotSupportedException> .

<sup>2</sup> in MacOS <xref:System.Security.Cryptography.RSAOpenSsl> funziona se OpenSSL è installato ed è possibile trovare un dylib libcrypto appropriato tramite il caricamento dinamico della libreria. Se non è possibile trovare una libreria appropriata, verranno generate eccezioni.

### <a name="ecdsa"></a>ECDSA

ECDSA (algoritmo di firma digitale a curva ellittica) viene eseguita dalle librerie del sistema operativo ed è soggetta alle limitazioni di dimensione e alle caratteristiche delle prestazioni.

Le curve della chiave ECDSA sono definite dalle librerie del sistema operativo e sono soggette alle limitazioni.

| Curva ellittica                     | Windows 10    | Windows 7-8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| Curve Brainpool (come curve denominate) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| Altre curve denominate                 | ⚠️<sup>2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| Curve esplicite                    | ✔️           | ❌              | ✔️           | ❌            |
| Esporta o importa come esplicito       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> le distribuzioni Linux non supportano tutte le stesse curve denominate.

<sup>2</sup> il supporto per le curve denominate è stato aggiunto a Windows CNG in Windows 10. Per altre informazioni, vedere [CNG denominate curve ellittiche](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Le curve denominate non sono disponibili nelle versioni precedenti di Windows, ad eccezione di tre curve in Windows 7.

<sup>3</sup> l'esportazione con parametri di curva espliciti richiede il supporto della libreria del sistema operativo, che non è disponibile in MacOS o nelle versioni precedenti di Windows.

#### <a name="ecdsa-native-interop"></a>Interoperabilità nativa ECDSA

.NET espone i tipi per consentire ai programmi di interagire con le librerie del sistema operativo utilizzate dal codice di crittografia .NET. I tipi necessari non vengono convertiti tra le piattaforme e devono essere usati direttamente solo quando necessario.

| Type                                             | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDsaCng>     | ✔️     | ❌    | ❌    |
| <xref:System.Security.Cryptography.ECDsaOpenSsl> | ❌     | ✔️    | ⚠️\*  |

\*In macOS <xref:System.Security.Cryptography.ECDsaOpenSsl> funziona se OpenSSL è installato nel sistema ed è possibile trovare un dylib libcrypto appropriato tramite il caricamento dinamico della libreria. Se non è possibile trovare una libreria appropriata, verranno generate eccezioni.

### <a name="ecdh"></a>ECDH

La generazione della chiave ECDH (Diffie-Hellman a curva ellittica) viene eseguita dalle librerie del sistema operativo ed è soggetta alle limitazioni di dimensione e alle caratteristiche delle prestazioni.

La <xref:System.Security.Cryptography.ECDiffieHellman> classe non restituisce il valore "Raw" del calcolo ECDH. Tutti i dati restituiti sono in termini di funzioni di derivazione della chiave:

* HASH (Z)
* HASH (anteporre | | Z | | aggiungere
* HMAC (chiave, Z)
* HMAC (chiave, anteporre | | Z | | aggiungere
* HMAC (Z, Z)
* HMAC (Z, Prepend | | Z | | aggiungere
* Tls11Prf (etichetta, valore di inizializzazione)

Le curve della chiave ECDH sono definite dalle librerie del sistema operativo e sono soggette alle limitazioni.

| Curva ellittica                     | Windows 10    | Windows 7-8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| curve Brainpool (come curve denominate) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| altre curve denominate                 | ⚠️<sup>2</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| curve esplicite                    | ✔️           | ❌              | ✔️           | ❌            |
| Esporta o importa come esplicito       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> le distribuzioni Linux non supportano tutte le stesse curve denominate.

<sup>2</sup> il supporto per le curve denominate è stato aggiunto a Windows CNG in Windows 10. Per altre informazioni, vedere [CNG denominate curve ellittiche](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Le curve denominate non sono disponibili nelle versioni precedenti di Windows, ad eccezione di tre curve in Windows 7.

<sup>3</sup> l'esportazione con parametri di curva espliciti richiede il supporto della libreria del sistema operativo, che non è disponibile in MacOS o nelle versioni precedenti di Windows.

#### <a name="ecdh-native-interop"></a>Interoperabilità nativa ECDH

.NET espone i tipi per consentire ai programmi di interagire con le librerie del sistema operativo utilizzate da .NET. I tipi necessari non vengono convertiti tra le piattaforme e devono essere usati direttamente solo quando necessario.

| Type                                                       | Windows | Linux | macOS |
|------------------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDiffieHellmanCng>     | ✔️     | ❌    | ❌   |
| <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> | ❌     | ✔️    | ⚠️\* |

\*In macOS <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> funziona se è installato openssl ed è possibile trovare un dylib libcrypto appropriato tramite il caricamento dinamico della libreria. Se non è possibile trovare una libreria appropriata, verranno generate eccezioni.

### <a name="dsa"></a>DSA

La generazione della chiave DSA (Digital Signature Algorithm) viene eseguita dalle librerie di sistema ed è soggetta alle limitazioni di dimensione e alle caratteristiche delle prestazioni.

| Funzione                      | CNG di Windows | Linux | macOS         | Windows CAPI |
|-------------------------------|-------------|-------|---------------|--------------|
| Creazione della chiave (<= 1024 bit)   | ✔️         | ✔️    | ❌            | ✔️           |
| Creazione della chiave (> 1024 bit)    | ✔️         | ✔️    | ❌            | ❌            |
| Caricamento delle chiavi (<= 1024 bit)   | ✔️         | ✔️    | ✔️            | ✔️           |
| Caricamento di chiavi (> 1024 bit)    | ✔️         | ✔️    | ⚠️\*          | ❌            |
| FIPS 186-2                    | ✔️         | ✔️    | ✔️            | ✔️           |
| FIPS 186-3 (firme SHA-2) | ✔️         | ✔️    | ❌            | ❌            |

\*macOS carica le chiavi DSA maggiori di 1024 bit, ma il comportamento di tali chiavi non è definito. Non si comportano in base allo standard FIPS 186-3.

#### <a name="dsa-on-windows"></a>DSA per Windows

* Windows CryptoAPI (CAPI) viene usato ogni volta che [`new DSACryptoServiceProvider()`](xref:System.Security.Cryptography.DSACryptoServiceProvider) viene usato.
* Viene utilizzata l'API Cryptography Next Generation (CNG) quando [`new DSACng()`](xref:System.Security.Cryptography.DSACng) si utilizza.
* L'oggetto restituito da <xref:System.Security.Cryptography.DSA.Create%2A?displayProperty=nameWithType> è alimentato internamente da Windows CNG. Questo utilizzo di Windows CNG è un dettaglio di implementazione ed è soggetto a modifiche.
* Il <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A> metodo di estensione per <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> restituisce un' <xref:System.Security.Cryptography.DSACng> istanza di. Questo utilizzo di <xref:System.Security.Cryptography.DSACng> è un dettaglio di implementazione ed è soggetto a modifiche.
* Il <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A> metodo di estensione per <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> preferisce un' <xref:System.Security.Cryptography.DSACng> istanza, ma se <xref:System.Security.Cryptography.DSACng> non è in grado di aprire la chiave, verrà effettuato un <xref:System.Security.Cryptography.DSACryptoServiceProvider> tentativo.  Il provider preferito è un dettaglio di implementazione ed è soggetto a modifiche.

#### <a name="dsa-native-interop"></a>Interoperabilità nativa DSA

.NET espone i tipi per consentire ai programmi di interagire con le librerie del sistema operativo utilizzate dal codice di crittografia .NET. I tipi necessari non vengono convertiti tra le piattaforme e devono essere usati direttamente solo quando necessario.

| Type                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.DSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup> | ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.DSACng>                   | ✔️     | ❌             | ❌            |
| <xref:System.Security.Cryptography.DSAOpenSsl>               | ❌      | ✔️            | ⚠️<sup>2</sup> |

<sup>1</sup> in MacOS e Linux <xref:System.Security.Cryptography.DSACryptoServiceProvider> può essere usato per la compatibilità con i programmi esistenti. In tal caso, qualsiasi metodo che richiede l'interoperabilità di sistema, ad esempio l'apertura di una chiave denominata, genera un'eccezione <xref:System.PlatformNotSupportedException> .

<sup>2</sup> in MacOS <xref:System.Security.Cryptography.DSAOpenSsl> funziona se OpenSSL è installato ed è possibile trovare un dylib libcrypto appropriato tramite il caricamento dinamico della libreria. Se non è possibile trovare una libreria appropriata, verranno generate eccezioni.

## <a name="x509-certificates"></a>Certificati X.509

La maggior parte del supporto per i certificati X. 509 in .NET deriva dalle librerie del sistema operativo. Per caricare un certificato in un' <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> istanza di o <xref:System.Security.Cryptography.X509Certificates.X509Certificate> in .NET, il certificato deve essere caricato dalla libreria del sistema operativo sottostante.

### <a name="read-a-pkcs12pfx"></a>Leggi un PKCS12/PFX

| Scenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Vuoto                                        | ✔️     | ✔️    | ✔️   |
| Un certificato, nessuna chiave privata              | ✔️     | ✔️    | ✔️   |
| Un certificato con chiave privata            | ✔️     | ✔️    | ✔️   |
| Più certificati, nessuna chiave privata       | ✔️     | ✔️    | ✔️   |
| Più certificati, una chiave privata       | ✔️     | ✔️    | ✔️   |
| Più certificati, chiavi private multiple | ✔️     | ⚠️\*  | ✔️   |

\*Disponibile nelle versioni di anteprima di .NET 5.

### <a name="write-a-pkcs12pfx"></a>Scrivere un PKCS12/PFX

| Scenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Vuoto                                        | ✔️     | ✔️    | ⚠️\* |
| Un certificato, nessuna chiave privata              | ✔️     | ✔️    | ⚠️\* |
| Un certificato con chiave privata            | ✔️     | ✔️    | ✔️   |
| Più certificati, nessuna chiave privata       | ✔️     | ✔️    | ⚠️\* |
| Più certificati, una chiave privata       | ✔️     | ✔️    | ✔️   |
| Più certificati, chiavi private multiple | ✔️     | ⚠️\*  | ✔️   |
| Caricamento temporaneo                            | ✔️     | ✔️    | ⚠️\* |

\*Disponibile nelle versioni di anteprima di .NET 5.

macOS non è in grado di caricare chiavi private del certificato senza un oggetto keychain, che richiede la scrittura su disco. I Keychain vengono creati automaticamente per il caricamento PFX e vengono eliminati quando non sono più in uso. Poiché l' <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> opzione indica che la chiave privata non deve essere scritta su disco, l'asserzione di tale flag in MacOS restituisce un <xref:System.PlatformNotSupportedException> .

### <a name="write-a-pkcs7-certificate-collection"></a>Scrivere una raccolta di certificati PKCS7

Windows e Linux emettono BLOB PKCS7 con codifica DER. macOS genera BLOB PKCS7 codificati a lunghezza indefinita.

### <a name="x509store"></a>X509Store

In Windows, la <xref:System.Security.Cryptography.X509Certificates.X509Store> classe è una rappresentazione delle API dell'archivio certificati Windows. Queste API funzionano in .NET Core e .NET 5 come in .NET Framework.

In Linux, la <xref:System.Security.Cryptography.X509Certificates.X509Store> classe è una proiezione di decisioni di attendibilità del sistema (di sola lettura), le decisioni di attendibilità utente (lettura-scrittura) e l'archiviazione delle chiavi utente (lettura/scrittura).

In macOS, la <xref:System.Security.Cryptography.X509Certificates.X509Store> classe è una proiezione di decisioni di attendibilità del sistema (di sola lettura), le decisioni di attendibilità utente (sola lettura) e l'archiviazione delle chiavi utente (lettura/scrittura).

Nelle tabelle seguenti vengono illustrati gli scenari supportati in ogni piattaforma. Per gli scenari non supportati ( ❌ nelle tabelle) <xref:System.Security.Cryptography.CryptographicException> viene generata un'eccezione.

#### <a name="the-my-store"></a>Archivio personale

| Scenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Apri CurrentUser\My (ReadOnly)                   | ✔️     | ✔️    | ✔️   |
| Apri CurrentUser\My (ReadWrite)                  | ✔️     | ✔️    | ✔️   |
| Apri CurrentUser\My (ExistingOnly)               | ✔️     | ⚠️    | ✔️   |
| Apri LocalMachine\My                             | ✔️     | ❌    | ✔️   |

In Linux, gli archivi vengono creati durante la prima scrittura e non esistono archivi utente per impostazione predefinita, pertanto l'apertura `CurrentUser\My` con `ExistingOnly` può non riuscire.

In macOS, l' `CurrentUser\My` archivio è il keychain predefinito dell'utente, che è `login.keychain` per impostazione predefinita. L' `LocalMachine\My` archivio è `System.keychain` .

#### <a name="the-root-store"></a>Archivio radice

| Scenario                              | Windows | Linux | macOS           |
|---------------------------------------|---------|-------|-----------------|
| Apri CurrentUser\Root (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Apri CurrentUser\Root (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Apri CurrentUser\Root (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (se ReadOnly) |
| Apri LocalMachine\Root (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Apri LocalMachine\Root (ReadWrite)    | ✔️     | ❌    | ❌              |
| Apri LocalMachine\Root (ExistingOnly) | ✔️     | ⚠️    | ✔️ (se ReadOnly) |

In Linux, l' `LocalMachine\Root` archivio è un'interpretazione del bundle CA nel percorso predefinito per OpenSSL.

In macOS, l' `CurrentUser\Root` archivio è un'interpretazione dei `SecTrustSettings` Risultati per il dominio di attendibilità utente. L' `LocalMachine\Root` archivio è un'interpretazione dei `SecTrustSettings` Risultati per i domini amministratore e trust di sistema.

#### <a name="the-intermediate-store"></a>Archivio intermedio

| Scenario                                      | Windows | Linux | macOS           |
|-----------------------------------------------|---------|-------|-----------------|
| Apri CurrentUser\Intermediate (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Apri CurrentUser\Intermediate (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Apri CurrentUser\Intermediate (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (se ReadOnly) |
| Apri LocalMachine\Intermediate (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Apri LocalMachine\Intermediate (ReadWrite)    | ✔️     | ❌    | ❌              |
| Apri LocalMachine\Intermediate (ExistingOnly) | ✔️     | ⚠️    | ✔️ (se ReadOnly) |

In Linux l' `CurrentUser\Intermediate` archivio viene usato come cache quando si scaricano le autorità di certificazione intermedie in base ai record di accesso alle informazioni sull'autorità per le compilazioni X509Chain riuscite L' `LocalMachine\Intermediate` archivio è un'interpretazione del bundle CA nel percorso predefinito per OpenSSL.

#### <a name="the-disallowed-store"></a>Archivio non consentito

| Scenario                                    | Windows | Linux | macOS           |
|---------------------------------------------|---------|-------|-----------------|
| Apri CurrentUser\Disallowed (ReadOnly)      | ✔️     | ⚠️    | ✔️             |
| Apri CurrentUser\Disallowed (ReadWrite)     | ✔️     | ⚠️    | ❌              |
| Apri CurrentUser\Disallowed (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (se ReadOnly) |
| Apri LocalMachine\Disallowed (ReadOnly)     | ✔️     | ❌    | ✔️             |
| Apri LocalMachine\Disallowed (ReadWrite)    | ✔️     | ❌    | ❌              |
| Apri LocalMachine\Disallowed (ExistingOnly) | ✔️     | ❌    | ✔️ (se ReadOnly) |

In Linux l' `Disallowed` archivio non viene usato nella compilazione a catena e il tentativo di aggiungervi contenuti comporta un <xref:System.Security.Cryptography.CryptographicException> . <xref:System.Security.Cryptography.CryptographicException>Viene generata un'eccezione quando si apre l' `Disallowed` archivio se il contenuto è già stato acquisito.

In macOS gli archivi CurrentUser\Disallowed e LocalMachine\Disallowed sono interpretazioni dei risultati SecTrustSettings appropriati per i certificati il cui trust è impostato su `Always Deny` .

#### <a name="nonexistent-store"></a>Archivio non esistente

| Scenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Apri archivio non esistente (ExistingOnly)           | ❌     | ❌     | ❌    |
| Apri archivio CurrentUser non esistente (ReadWrite)  | ✔️     | ✔️     | ⚠️   |
| Archivio non esistente LocalMachine aperto (ReadWrite) | ✔️     | ❌     | ❌    |

In macOS la creazione di un archivio personalizzato con l'API X509Store è supportata solo per la `CurrentUser` località. Verrà creato un nuovo keychain senza password nella directory Keychain dell'utente (*~/Library/Keychains*). Per creare un keychain con la password, è possibile usare un P/Invoke in `SecKeychainCreate` . Analogamente, `SecKeychainOpen` è possibile usare per aprire keychain in posizioni diverse. Il risultato `IntPtr` può essere passato a [`new X509Store(IntPtr)`](xref:System.Security.Cryptography.X509Certificates.X509Store.%23ctor(System.IntPtr)) per ottenere un archivio in grado di leggere/scrivere, soggetto alle autorizzazioni dell'utente corrente.

### <a name="x509chain"></a>X509Chain

macOS non supporta l'utilizzo di CRL offline, pertanto `X509RevocationMode.Offline` viene considerato come `X509RevocationMode.Online` .

macOS non supporta il download di timeout avviato dall'utente in CRL (elenco di revoche di certificati)/OCSP (protocollo di stato del certificato online)/AIA (accesso alle informazioni di autorità), pertanto `X509ChainPolicy.UrlRetrievalTimeout` viene ignorato.

## <a name="additional-resources"></a>Risorse aggiuntive

* [Modello di crittografia .NET](cryptography-model.md)
* [Servizi di crittografia .NET](cryptographic-services.md)
