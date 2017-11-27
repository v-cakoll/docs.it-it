---
title: Sicurezza di SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4f41a794916c63672ca0c844f086629f77b90aa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-security"></a>Sicurezza di SQL Server
In [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] sono disponibili molte funzionalità che supportano la creazione di applicazioni di database protette.  
  
 Indipendentemente dalla versione di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] in uso, esistono problemi di sicurezza, ad esempio furto dei dati o vandalismo, che è opportuno considerare. Anche l'integrità dei dati rientra tra i problemi di sicurezza da considerare. Se i dati non sono protetti, potrebbero diventare inutili se ne viene consentita la modifica ad hoc e vengono modificati con valori incorretti oppure eliminati, inavvertitamente o intenzionalmente. È inoltre spesso necessario garantire la conformità a requisiti di carattere legale, ad esempio la corretta archiviazione di informazioni riservate. A seconda delle leggi in vigore in una determinata giurisdizione, è infatti assolutamente vietata l'archiviazione di alcuni tipi di dati personali.  
  
 Ogni versione di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], così come ogni versione di Windows, include funzionalità di sicurezza diverse e ogni nuova versione presenta funzionalità più avanzate rispetto alle versioni precedenti. È importante comprendere che le sole funzionalità di sicurezza non bastano a garantire un'applicazione di database protetta. Ogni applicazione di database è diversa dall'altra per requisiti, ambiente di esecuzione, modello di distribuzione, posizione fisica e popolazione di utenti. Alcune applicazioni con ambito locale possono richiedere un livello minimo di sicurezza, mentre per altre applicazioni locali o distribuite tramite Internet può essere necessario adottare misure di sicurezza severe, nonché funzionalità per la valutazione e il monitoraggio continuo della sicurezza.  
  
 I requisiti di sicurezza di un'applicazione di database [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] devono essere considerati già in fase di progettazione e non in un secondo momento. La valutazione delle minacce nelle prime fasi del ciclo di sviluppo consente di ridurre al minimo possibili danni qualora venga rilevata una vulnerabilità.  
  
 Anche se la progettazione iniziale di un'applicazione è corretta, possono emergere nuove minacce con l'evoluzione del sistema. La creazione di più linee di difesa intorno al database consente di ridurre al minimo i danni causati da una violazione del sistema di sicurezza. La prima linea di difesa consiste nel ridurre l'area soggetta a possibili attacchi non concedendo mai un numero di autorizzazioni maggiore di quello assolutamente necessario.  
  
 Negli argomenti di questa sezione viene fornita una breve descrizione delle funzionalità di sicurezza di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] pertinenti per gli sviluppatori, con collegamenti ai relativi argomenti della documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] e ad altre risorse di approfondimento.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica della sicurezza SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Vengono descritte l'architettura e le funzionalità di sicurezza di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Scenari di sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Sono contenuti argomenti che illustrano diversi scenari di sicurezza per applicazioni ADO.NET e [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Sicurezza SQL Server Express](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Vengono illustrate le considerazioni sulla sicurezza relative a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sicurezza e protezione (motore di Database)](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)  
 Argomenti sulla sicurezza della documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Considerazioni sulla sicurezza per SQL Server](http://go.microsoft.com/fwlink/?LinkId=98587)  
 Argomenti sulla sicurezza della documentazione online di [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
