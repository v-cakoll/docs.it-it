---
title: Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 507de3ca635986d1f4e0e3ba7c607a4af774cdcf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716272"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10

Il .NET Framework 1,1 non è supportato nei sistemi operativi Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10. In alcuni casi, .NET Framework 1.1 viene identificato specificamente come obbligatorio per l'esecuzione di un'app. In questi casi è necessario contattare il fornitore di software indipendente (ISV), per aggiornare l'app e poterla eseguire in .NET Framework 3.5 SP1 o versioni successive. Per altre informazioni, vedere [Migrazione da .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Installare .NET Framework 1.1 da un CD o dall'Area download

Non è possibile installare manualmente il .NET Framework 1,1 in Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10. e non è più supportato. Se si tenta di installare il pacchetto, viene visualizzato il seguente messaggio di errore: "Impossibile continuare. La versione corrente di .NET Framework è incompatibile con una versione precedentemente installata". Per risolvere questo problema, installare [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22). Questa versione include la .NET Framework 2,0 (la versione che segue il .NET Framework 1,1), supportata in Windows 8, Windows 8.1 e Windows 10. È consigliabile iniziare sempre installando l'app per determinare se viene aggiornata automaticamente a una versione successiva di .NET Framework. In caso contrario, contattare il fornitore di software indipendente (ISV) per un aggiornamento dell'app.

## <a name="see-also"></a>Vedere anche

- [Migrazione da .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](dotnet-35-windows-10.md)
