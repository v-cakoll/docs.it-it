---
title: Classe UnsafeNclNativeMethods (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.UnsafeNclNativeMethods
- System.Net.UnsafeNclNativeMethods.NativePKI
- System.Net.UnsafeNclNativeMethods.NativePKI.FindClientCertificates
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 46756a0d1d69b4768dbb8dcdd7ab098d3f1849bf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990359"
---
# <a name="unsafenclnativemethods-class"></a>Classe UnsafeNclNativeMethods

Contiene classi che importano metodi di rete nativi non sicuri. Questa classe non può essere ereditata.

```csharp
internal static class UnsafeNclNativeMethods
```

> [!WARNING]
> Questa classe è interna e non è destinata all'uso diretto nel codice.
>
> Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.

## <a name="nativepki-class"></a>Classe NativePKI

Contiene i metodi importati da crypt32.dll. Questi metodi gestiscono i certificati quando si usa Hypertext Transfer Protocol Secure (HTTPS). Questa classe non può essere ereditata.

```csharp
internal static class NativePKI
```

## <a name="nativepkifindclientcertificates-method"></a>NativePKI. FindClientCertificates, metodo

Individua i certificati client disponibili da inviare al server.

```csharp
internal static X509CertificateCollection FindClientCertificates
```

### <a name="return-value"></a>Valore restituito

<xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection?displayProperty=nameWithType>

Raccolta di certificati client disponibili.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** Sistema (in System.dll)
