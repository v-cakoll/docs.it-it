---
title: Ricerca dello strumento di chiave privata (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 00ad27d28ee3a589d5ee8702bd036b05d8ceb4b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637564"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Ricerca dello strumento di chiave privata (FindPrivateKey.exe)

Questo strumento da riga di comando può essere usato per recuperare una chiave privata da un archivio certificati. Ad esempio, *FindPrivateKey.exe* può essere utilizzato per trovare il percorso e nome del file della chiave privato associato a un certificato X.509 specifico nell'archivio certificati.

> [!IMPORTANT]
> Lo strumento FindPrivateKey viene fornito come esempio WCF. Per altre informazioni su dove trovare il codice di esempio e su come compilare la soluzione, vedere [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Sintassi

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>Note

Nelle tabelle seguenti vengono descritti gli argomenti e le opzioni che possono essere usati con lo strumento di Ricerca della Chiave Privata (FindPrivateKey.exe).

|Argomento|Descrizione|
|--------------|-----------------|
|`storeName`|Nome dell'archivio certificati.|
|`storeLocation`|Percorso dell'archivio certificati.|

|Opzione|Descrizione|
|------------|-----------------|
|`/n <` *subjectName* `>`|Specifica il nome dell’oggetto del certificato.|
|`/t <` *thumbprint* `>`|Specifica l'identificazione digitale del certificato. Usare Certmgr.exe per recuperare l'identificazione digitale del certificato.|
|`/f`|Restituisce soltanto il nome file.|
|`/d`|Restituisce soltanto la directory.|
|`/a`|Restituisce il nome file assoluto.|

## <a name="examples"></a>Esempi

Il comando seguente recupera la chiave privata per John Doe:

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

Il comando seguente recupera la chiave privata per il computer locale:

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
