---
title: Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10
description: Viene descritto come supportare le app che richiedono .NET Framework 1.1, che non è più supportato in molte versioni del sistema operativo Windows.
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111790"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Eseguire app .NET Framework 1.1 in Windows 8, Windows 8.1 o Windows 10

.NET Framework 1.1 non è supportato nei sistemi operativi Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10. In alcuni casi, .NET Framework 1.1 è necessario per l'esecuzione di un'app. In questi casi, contattare il fornitore di software indipendente (ISV) per aggiornare l'app per l'esecuzione in .NET Framework 3.5 SP1 o versione successiva. Per ulteriori informazioni, vedere [Migrazione da .NET Framework 1.1.](../migration-guide/migrating-from-the-net-framework-1-1.md)

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a>Installare .NET Framework 1.1 da un CD o da un'area download

Non è possibile installare manualmente .NET Framework 1.1 in Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 o Windows 10 da un CD o da un'area download. Non è più supportato. Se si tenta di installare il pacchetto, viene visualizzato il seguente messaggio di errore: "Impossibile continuare. La versione corrente di .NET Framework è incompatibile con una versione precedentemente installata". Per risolvere questo problema, installare [.NET Framework 3.5 SP1](https://www.microsoft.com/download/details.aspx?id=22). Questa versione include .NET Framework 2.0 (la versione che segue .NET Framework 1.1), che è supportata in Windows 8, Windows 8.1 e Windows 10. È sempre consigliabile provare a installare prima l'app per determinare se verrà aggiornata automaticamente a una versione successiva di .NET Framework. In caso contrario, contatta l'ISV per un aggiornamento dell'app.

## <a name="see-also"></a>Vedere anche

- [Migrazione da .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](dotnet-35-windows-10.md)
