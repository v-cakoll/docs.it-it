---
title: Registrazione di assembly presso COM
description: Registrare o annullare la registrazione di assembly con COM usando lo strumento di registrazione degli assembly (Regasm.exe), che aggiunge informazioni sulla classe al registro di sistema.
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
ms.openlocfilehash: 1b73a79b8167e7f75b8c68f708179e88c575d66a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621899"
---
# <a name="registering-assemblies-with-com"></a>Registrazione di assembly presso COM
È possibile eseguire uno strumento da riga di comando denominato [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) per registrare o annullare la registrazione di un assembly per l'uso con COM. Regasm.exe aggiunge informazioni sulla classe al Registro di sistema, così che i client COM possano usare la classe di .NET Framework in modo trasparente. La classe <xref:System.Runtime.InteropServices.RegistrationServices> fornisce funzionalità equivalenti.  
  
 Un componente gestito deve essere registrato nel Registro di sistema di Windows per poter essere attivato da un client COM. La tabella seguente mostra le chiavi che Regasm.exe aggiunge in genere al Registro di sistema di Windows. 000000 indica il valore GUID effettivo.  
  
|GUID|Descrizione|Chiave del Registro di sistema|  
|----------|-----------------|------------------|  
|CLSID|Identificatore di classe|HKEY_CLASSES_ROOT\CLSID\\{000…000}|  
|IID|Identificatore di interfaccia|HKEY_CLASSES_ROOT\Interface\\{000…000}|  
|LIBID|Identificatore di libreria|HKEY_CLASSES_ROOT\TypeLib\\{000…000}|  
|ProgID|Identificatore a livello di codice|HKEY_CLASSES_ROOT\000…000|  
  
 Nella chiave HKCR\CLSID\\{0000…0000} il valore predefinito viene impostato sull'oggetto ProgID della classe e vengono aggiunti due valori denominati, Class e Assembly. Il runtime legge il valore di Assembly dal Registro di sistema e lo passa al resolver di assembly di runtime. Il resolver di assembly cerca di individuare l'assembly, in base alle informazioni sull'assembly come il nome e il numero di versione. Affinché il resolver possa individuare un assembly, l'assembly deve trovarsi in una delle posizioni seguenti:  
  
- Global Assembly Cache (l'assembly deve avere un nome sicuro).  
  
- directory dell'applicazione. Gli assembly caricati dal percorso dell'applicazione sono accessibili solo da tale applicazione.  
  
- Percorso specificato con l'opzione **/codebase** in Regasm.exe.  
  
 Regasm.exe crea anche la chiave InProcServer32 nella chiave HKCR\CLSID\\{0000…0000}. Il valore predefinito per la chiave è impostato sul nome della DLL che inizializza Common Language Runtime (Mscoree.dll).  
  
## <a name="examining-registry-entries"></a>Esame delle voci del Registro di sistema  
 L'interoperabilità COM fornisce un'implementazione di class factory standard per creare un'istanza di qualsiasi classe .NET Framework. I client possono chiamare **DllGetClassObject** sulla DLL gestita per ottenere una class factory e creare oggetti, esattamente come accade con qualsiasi altro componente COM.  
  
 Per la sottochiave `InprocServer32`, viene visualizzato un riferimento a Mscoree.dll al posto di una libreria dei tipi COM tradizionale per indicare che Common Language Runtime crea l'oggetto gestito.  
  
## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti .NET Framework a COM](exposing-dotnet-components-to-com.md)
- [Procedura: Fare riferimento a tipi .NET da COM](how-to-reference-net-types-from-com.md)
- [Chiamata di un oggetto .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Distribuzione di un'applicazione per l'accesso COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
