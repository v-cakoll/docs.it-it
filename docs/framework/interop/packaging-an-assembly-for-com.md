---
title: Creazione di un pacchetto di un assembly .NET Framework per COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
ms.openlocfilehash: 6866da283cc7cdd180aada252007d67bd72cd862
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124100"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a>Creazione di un pacchetto di un assembly .NET Framework per COM

Gli sviluppatori COM possono trarre vantaggio dalle informazioni seguenti sui tipi gestiti che prevedono di incorporare nella propria applicazione:

- Un elenco dei tipi utilizzabili dalle applicazioni COM

  Alcuni tipi gestiti non sono visibili per COM. Alcuni sono visibili, ma non generabili e alcuni sono sia visibili che generabili. Un assembly può contenere qualsiasi combinazione di tipi invisibili, visibili, non generabili e generabili. Per motivi di completezza, identificare i tipi in un assembly che si desidera esporre a COM, soprattutto quando tali tipi sono un subset dei tipi esposti a .NET Framework.

  Per altre informazioni, vedere [Qualificazione di tipi .NET per l'interoperabilità](../../standard/native-interop/qualify-net-types-for-interoperation.md).

- Istruzioni di controllo delle versioni

  Le classi gestite che implementano l'interfaccia di classe (interfaccia generata dall'interoperabilità COM) sono soggette a restrizioni di controllo delle versioni.

  Per linee guida sull'uso dell'interfaccia della classe, vedere [Introduzione all'interfaccia della classe](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).

- Istruzioni per la distribuzione

  Gli assembly con nome sicuro firmati da un editore possono essere installati nella Global Assembly Cache. Gli assembly non firmati devono essere installati nel computer dell'utente come assembly privati.

  Per altre informazioni, vedere [Considerazioni sulla sicurezza degli assembly](../../standard/assembly/security-considerations.md).

- Inclusione di una libreria dei tipi

  La maggior parte dei tipi richiede una libreria dei tipi per l'uso da un'applicazione COM. È possibile generare una libreria dei tipi o delegare agli sviluppatori COM questa operazione. Windows SDK include le opzioni seguenti per la generazione di una libreria dei tipi:

  - [Utilità di esportazione della libreria dei tipi](#cpconpackagingassemblyforcomanchor1)

  - [Classe TypeLibConverter](#cpconpackagingassemblyforcomanchor2)

  - [Strumento di registrazione degli assembly](#cpconpackagingassemblyforcomanchor3)

  - [Strumento di installazione dei servizi .NET](#cpconpackagingassemblyforcomanchor4)

  Indipendentemente dal meccanismo scelto, solo i tipi pubblici definiti nell'assembly specificato vengono inclusi nella libreria dei tipi generata.

Per istruzioni, vedere [Procedura: incorporare librerie dei tipi come risorse Win32 nelle applicazioni basate su .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a>Utilità di esportazione della libreria dei tipi

[Tlbexp.exe (utilità di esportazione della libreria dei tipi)](../tools/tlbexp-exe-type-library-exporter.md) è uno strumento da riga di comando che converte le classi e le interfacce contenute in un assembly in una libreria dei tipi COM. Quando le informazioni sui tipi della classe sono disponibili, i client COM possono creare un'istanza della classe .NET e chiamare i metodi dell'istanza, come se si trattasse di un oggetto COM. Tlbexp.exe converte un intero assembly in una sola volta. Non è possibile utilizzare Tlbexp.exe per generare informazioni sui tipi per un sottoinsieme dei tipi definiti in un assembly.

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a>Classe TypeLibConverter

La classe <xref:System.Runtime.InteropServices.TypeLibConverter>, inclusa nello spazio dei nomi **System.Runtime.Interop**, converte le classi e interfacce contenute in un assembly in una libreria dei tipi COM. Questa API genera le stesse informazioni sui tipi dell'utilità di esportazione della libreria dei tipi, descritta nella sezione precedente.

La **classe TypeLibConverter** implementa <xref:System.Runtime.InteropServices.ITypeLibConverter>.

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a>Strumento di registrazione degli assembly

Lo [strumento di registrazione degli assembly (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) può generare e registrare una libreria dei tipi quando si applica l'opzione **/tlb:**. I client COM richiedono l'installazione di librerie dei tipi nel Registro di sistema di Windows. Senza questa opzione, Regasm.exe registra solo i tipi in un assembly, non la libreria dei tipi. Registrare i tipi in un assembly e la registrazione della libreria dei tipi sono due attività distinte.

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a>Strumento di installazione dei servizi .NET

Lo [strumento di installazione dei servizi .NET (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) aggiunge classi gestite ai servizi componenti di Windows 2000 e combina diverse attività in un unico strumento. Oltre a caricamento e registrazione di un assembly, Regsvcs.exe può generare, registrare e installare la libreria dei tipi in un'applicazione COM+ 1.0 esistente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [Esposizione di componenti .NET Framework a COM](exposing-dotnet-components-to-com.md)
- [Qualificazione di tipi .NET per l'interoperabilità](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [Introduzione all'interfaccia della classe](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [Considerazioni sulla sicurezza degli assembly](../../standard/assembly/security-considerations.md)
- [Tlbexp. exe (utilità di esportazione della libreria di tipi)](../tools/tlbexp-exe-type-library-exporter.md)
- [Registrazione di assembly presso COM](registering-assemblies-with-com.md)
- [Procedura: incorporare librerie dei tipi come risorse Win32 nelle applicazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))
