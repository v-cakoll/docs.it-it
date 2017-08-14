---
title: Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10
ms.custom: 
ms.date: 05/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: c7b53a842dc4f9b6bfc04e058411e4a6d11a7bd1
ms.contentlocale: it-it
ms.lasthandoff: 08/05/2017

---

# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10

.NET Framework 1.1 non è supportato nei sistemi operativi [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] o Windows 10. In alcuni casi, .NET Framework 1.1 viene identificato specificamente come obbligatorio per l'esecuzione di un'app. In questi casi è necessario contattare il fornitore di software indipendente (ISV), per aggiornare l'app e poterla eseguire in [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] o versioni successive. Per altre informazioni, vedere [Migrazione da .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Installare .NET Framework 1.1 da un CD o dall'Area download

Non è possibile installare manualmente .NET Framework 1.1 in [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] o Windows 10. e non è più supportato. Se si tenta di installare il pacchetto, viene visualizzato il seguente messaggio di errore: "Impossibile continuare. La versione corrente di .NET Framework è incompatibile con una versione precedentemente installata". Per risolvere questo problema, installare [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22). Questa versione include .NET Framework 2.0 (la versione successiva a .NET Framework 1.1), che è supportata da [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] e Windows 10. È consigliabile iniziare sempre installando l'app per determinare se viene aggiornata automaticamente a una versione successiva di .NET Framework. In caso contrario, contattare il fornitore di software indipendente (ISV) per un aggiornamento dell'app.

## <a name="see-also"></a>Vedere anche

[Migrazione da .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)

