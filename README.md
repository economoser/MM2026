# ---------------------------------------------------------------------------------------------
# DESCRIPTION: This is the README file for the replication package for Morchio and Moser (2025)
# AUTHORS: Iacopo Morchio (University of Bristol) and Christian Moser (Columbia University)
# DATE: February 12, 2026
# ---------------------------------------------------------------------------------------------


# --------
# OVERVIEW
# --------

--- This README file describes the replication package associated with Morchio and Moser (2025) and is structured as follows:
      --- Data Availability and Provenance Statements
      --- Statements About Rights and PII
      --- License for Data and Codes
      --- Summary of Availability
      --- Details on Each Data Source
      --- Dataset List
      --- Computational Requirements
      --- Description of Replication Codes, Inputs, and Paper
            --- Replication Code Folder ~/code/cleaning_rais
                  --- Replication Code Folder ~/code/cleaning_rais/_7z
                  --- Replication Code Folder ~/code/cleaning_rais/_stata_packages
            --- Replication Code Folder ~/code/cleaning_orbis
                  --- Replication Code Folder ~/code/cleaning_orbis/_stata_packages
            --- Replication Code Folder ~/code/data
                  --- Replication Code Folder ~/code/data/_matlab_packages
                  --- Replication Code Folder ~/code/data/_stata_packages
            --- Replication Code Folder ~/code/model
                  --- Replication Code Folder ~/code/model/estimation
                  --- Replication Code Folder ~/code/model/solution
            --- Inputs Folder ~/inputs
            --- Paper Folder ~/paper
      --- Instructions to Replicators
      --- List of Tables and Programs
      --- References
      --- Acknowledgements

--- The code in this replication package conducts analyses based on data from seven data sources (Ministério da Economia, 2022; Instituto de Pesquisa Econômica Aplicada, 2019; Instituto de Pesquisa Econômica Aplicada, 2020; Engbom and Moser, 2022b; International Monetary Fund, 2022; Moody’s Analytics, 2025; Morchio and Moser, 2025) using Stata and MATLAB.

--- Three main files run all of the code, which is structured in three parts:
      --- Part 1: The first main file (~/code/cleaning_rais/RAIS_0_MASTER.do) generates a cleaned version of the confidential Relatório Anual de Informações Sociais (RAIS) data from Ministério da Economia (2022), drawing on Extended National Consumer Price Index (IPCA) data from Instituto de Pesquisa Econômica Aplicada (2019), minimum-wage data from Instituto de Pesquisa Econômica Aplicada (2020), and industry code crosswalks and occupation code crosswalks from Engbom and Moser (2022b).
      --- Part 2: The second main file (~/code/cleaning_orbis/ORBIS_0_MASTER.do) generates a cleaned version of the proprietary Orbis Historical data from Moody’s Analytics (2025), drawing on exchange-rate data from International Monetary Fund (2022).
      --- Part 3: The third main file (~/code/data/MM_0_MASTER.do) uses the processed RAIS data together with the processed Orbis Historical data and MATLAB inputs, consisting of initial guesses and precomputed results, from Morchio and Moser (2025) to produce all 237 exhibits, which comprise 70 figures, 41 tables, and 126 text snippets that are included in the paper.
      --- There is a fourth folder (~/code/model) with subdirectories containing several MATLAB routines, which will be automatically called by the third main file (~/code/data/MM_0_MASTER.do). There is no need to manually execute any of the routines in this folder.

--- Altogether, the entire replication package is expected to run for about 42 days:
      --- 34 days for part 1, cleaning the RAIS data
      --- 1 day for part 2, cleaning the Orbis Historical data
      --- 7 days for part 3, running all analyses and producing all exhibits contained in Morchio and Moser (2025)


# -------------------------------------------
# DATA AVAILABILITY AND PROVENANCE STATEMENTS
# -------------------------------------------

--- This paper involves the analysis of external data. The authors of Morchio and Moser (2025) are secondary data users---i.e., they did not generate the RAIS, Orbis Historical, or any other datasets for this project. Consequently, the data availability and provenance statements coincide.

--- The replication code files use the following seven datasets:
      --- RAIS from Ministério da Economia (2022)
      --- IPCA from Instituto de Pesquisa Econômica Aplicada (2019)
      --- Minimum wage from Instituto de Pesquisa Econômica Aplicada (2020)
      --- Industry code crosswalks and occupation code crosswalks from Engbom and Moser (2022b)
      --- Exchange rates from International Monetary Fund (2022)
      --- Orbis Historical from Moody’s Analytics (2025)
      --- Morchio and Moser (2025)

--- The RAIS data, in their identified form containing both worker and employer identifiers, are confidential and cannot be shared as part of this replication package. However, these data can be obtained upon submitting an application for data access to the Brazilian Ministry of the Economy (Ministério da Economia) via the Secretaria de Trabalho, Emprego e Previdência (website: https://www.gov.br/pt-br/servicos/solicitar-acesso-aos-dados-identificados-rais-e-caged). To enquire about data access, replicators may contact the Labor Statistics Dissemination Program of the Brazilian Ministério do Trabalho e Emprego, Secretaria de Políticas Públicas de Emprego, Coordenação Geral de Estatísticas do Trabalho at cget.sppe@mte.gov.br via email, at +55 61 3317 6667 by phone, or at +55 61 3317 8272 by fax. There are no costs associated with applying for the confidential RAIS data. However, a Technical Cooperation Agreement (Acordo de Cooperação Técnica, or ACT) or Cooperation Agreement (Acordo de Cooperação, or AC) must be signed. For this, researchers may be required to either establish an affiliation with a Brazilian public institution (e.g., university) or to establish a partnership between the Ministry and other qualifying entities.

--- The IPCA data are publicly available from Instituto de Pesquisa Econômica Aplicada (2019). For details, see the link provided in the "References" section below!

--- The minimum-wage data are publicly available from Instituto de Pesquisa Econômica Aplicada (2020). For details, see the link provided in the "References" section below!

--- The industry code crosswalks and occupation code crosswalks are publicly available from Engbom and Moser (2022b). For details, see the link provided in the "References" section below!

--- The exchange-rates data are publicly available from International Monetary Fund (2022). For details, see the link provided in the "References" section below!

--- The Orbis Historical data are proprietary data that have been purchased under an institutional user agreement through Columbia University. There is a cost associated with obtaining access to the proprietary Orbis Historical data from Moody's Analytics (website: https://www.moodys.com/web/en/us/capabilities/company-reference-data/orbis.html). To enquire about data access, replicators may contact Moody's Analytics, Client Service at clientservices@moodys.com via email or at +1 212 553 1653 by phone.

--- The MATLAB inputs, consisting of initial guesses and precomputed results, have been generated by Morchio and Moser (2025) and are disseminated as part of this replication package.


# -------------------------------
# STATEMENTS ABOUT RIGHTS AND PII
# -------------------------------

--- We certify that the authors of the manuscript have legitimate access to and permission to use the data used in this manuscript.

--- We certify that the authors of the manuscript have documented permission to redistribute/publish the data contained within this replication package. Appropriate permissions are documented in the LICENSE.txt file.

--- None of the data contained in the replication package comprise personally identifiable information (PII), implying that all variables in the replication package's data sets can be published without restrictions.


# --------------------------
# LICENSE FOR DATA AND CODES
# --------------------------

--- The data and codes are licensed under an MIT License. See LICENSE.txt for details.


# -----------------------
# SUMMARY OF AVAILABILITY
# -----------------------

--- Some data cannot be made publicly available.

--- Confidential and proprietary data used in this paper and not provided as part of the public replication package will be preserved for five years after publication, in accordance with journal policies.

--- The authors of the current paper will provide reasonable assistance to requests for clarification and replication.


# ---------------------------
# DETAILS ON EACH DATA SOURCE
# ---------------------------

--- The RAIS data from Ministério da Economia (2022) come in compressed .7z format. The cleaning routines in ~/code/cleaning_rais will automatically extract the raw data files and store them in Stata-native .dta format. These cleaning routines also contain a data dictionary in English, which is used to name and label all variables. These data are not provided as part of this replication package. The data files must be stored in ~/inputs/rais and contain subdirectories named after each year from 1985 to 2018. The raw data are characterized by the following codebook:
      --- anoadmissão (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- anochegada2 (numeric): 2010
      --- anochegadabrasil (numeric): 2011, 2012, 2013, 2015, 2016, 2017, 2018
      --- bairrossp (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- causaafastamento1 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- causaafastamento2 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- causaafastamento3 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- causadesli (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- causafast1 (numeric): 2007, 2008, 2009, 2010
      --- causafast2 (numeric): 2007, 2008, 2009, 2010
      --- causafast3 (numeric): 2007, 2008, 2009, 2010
      --- cbo94ocupação (mixed): 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cboocupação (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993
      --- cboocupação2002 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- ceivinc (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- ceivinculado (numeric): 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cepestab (numeric): 2015, 2016, 2017, 2018
      --- clascnae20 (mixed): 2006, 2007, 2008, 2009
      --- clascnae95 (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009
      --- cnae20classe (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cnae20subclasse (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cnae95classe (mixed): 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cnpjcei (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cnpjraiz (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- cpf (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- dataadmissãodeclarada (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- datadenascimento (numeric): 2014, 2015, 2016, 2017, 2018
      --- diadedesligamento (numeric): 2014, 2015, 2016, 2017, 2018
      --- diadesl (mixed): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- diafimaf1 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- diafimaf2 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- diafimaf3 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- diainiaf1 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- diainiaf2 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- diainiaf3 (mixed): 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- distritossp (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- dtadmissao (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- dtnasciment (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- empem3112 (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- escolaridadeapós2005 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- faixaetária (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- genero (string): 2005, 2006, 2007, 2008, 2009, 2010
      --- grauinstr (numeric): 2002, 2003, 2004, 2005, 2006, 2008
      --- grauinstrução20051985 (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- grinstrucao (numeric): 2007, 2008, 2009, 2010
      --- horascontr (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- ibgesubatividade (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994
      --- ibgesubsetor (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2015, 2016, 2017, 2018
      --- idade (numeric): 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- identificad (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- indalvara (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- indceivinc (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- indceivinculado (numeric): 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- indestabparticipapat (numeric): 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- indpat (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- indportadordefic (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- indsimples (numeric): 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- indsindical (numeric): 2017
      --- indtrabintermitente (numeric): 2017, 2018
      --- indtrabparcial (numeric): 2017, 2018
      --- indvínculoalvará (numeric): 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mesdeslig (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- mesfimaf1 (numeric): 2007, 2008, 2009, 2010
      --- mesfimaf2 (numeric): 2007, 2008, 2009, 2010
      --- mesfimaf3 (numeric): 2007, 2008, 2009, 2010
      --- mesiniaf1 (numeric): 2007, 2008, 2009, 2010
      --- mesiniaf2 (numeric): 2007, 2008, 2009, 2010
      --- mesiniaf3 (numeric): 2007, 2008, 2009, 2010
      --- motivodesligamento (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- municipio (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- município (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- muntrab (numeric): 2015, 2016, 2017, 2018
      --- mêsadmissão (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- mêsdesligamento (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsfimaf1 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsfimaf2 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsfimaf3 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsiniaf1 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsiniaf2 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- mêsiniaf3 (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- nacionalidad (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- nacionalidade (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- natjuridica (numeric): 2008, 2009, 2010
      --- naturezajurídica (mixed): 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- naturjur (numeric): 2002, 2003, 2004, 2005, 2006, 2007
      --- nome (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- nometrabalhador (string): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- numctps (numeric): 2002
      --- numectps (numeric): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- númeroctps (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- ocup2002 (string): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- ocupacao (string): 2002
      --- ocupacao94 (string): 2003, 2004, 2005, 2006, 2007, 2008, 2009
      --- pis (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- portdefic (numeric): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- qtddiasafastamento (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- qtdhoracontr (numeric): 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- qtdiasafas (numeric): 2007, 2008, 2009, 2010
      --- raca_cor (numeric): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- radiccnpj (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- razãosocial (string): 2015, 2016, 2017, 2018
      --- raçacor (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- remdezembro (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- remdezr (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- remmedia (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- remmedr (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- salcontr (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- sbclas20 (numeric): 2006, 2007, 2008, 2009, 2010
      --- sexo (numeric): 2002, 2003, 2004
      --- sexotrabalhador (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- situaçãovínculo (string): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993
      --- tamanhoestabelecimento (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tamestab (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- tempempr (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- tempoemprego (string): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tipoadm (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- tipoadmissão (numeric): 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tipodefic (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tipoestab (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tipoestbid (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009
      --- tipoestbl (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- tiposal (numeric): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- tiposalário (numeric): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tipovínculo (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- tpdefic (numeric): 2006, 2007, 2008, 2009, 2010
      --- tpvincl (string): 2002
      --- tpvinculo (numeric): 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- uf (mixed): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001
      --- ultrem (string): 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010
      --- v77 (numeric): 2016, 2017
      --- vlremabrilcc (string): 2015, 2016, 2017, 2018
      --- vlremagostocc (string): 2015, 2016, 2017, 2018
      --- vlremfevereirocc (string): 2015, 2016, 2017, 2018
      --- vlremjaneirocc (string): 2015, 2016, 2017, 2018
      --- vlremjulhocc (string): 2015, 2016, 2017, 2018
      --- vlremjunhocc (string): 2015, 2016, 2017, 2018
      --- vlremmaiocc (string): 2015, 2016, 2017, 2018
      --- vlremmarçocc (string): 2015, 2016, 2017, 2018
      --- vlremnovembrocc (string): 2015, 2016, 2017, 2018
      --- vlremoutubrocc (string): 2015, 2016, 2017, 2018
      --- vlremsetembrocc (string): 2015, 2016, 2017, 2018
      --- vlremundezembronom (string): 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vlremundezembrosm (string): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vlremunmédianom (string): 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vlremunmédiasm (string): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vlsaláriocontratual (string): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vlúltimaremuneraçãoano (string): 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018
      --- vínculoativo3112 (numeric): 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018

--- The IPCA data from Instituto de Pesquisa Econômica Aplicada (2019) come in Microsoft Excel-native .xls format. The raw data contain two variables or columns: The first column "Data" is the year and month in YYYY.MM format, while the second column "IPCA - geral - índice (dez. 1993 = 100) - - - Instituto Brasileiro de Geografia e Estatística, Sistema Nacional de Índices de Preços ao Consumidor (IBGE/SNIPC) - PRECOS12_IPCA12 -" is the actual value of the IPCA. The cleaning routines in ~/code/cleaning_rais process this raw .xls file and produce two Stata-native .dta files: cpi_bra.dta for a monthly IPCA data series and cpi_bra_yearly.dta for a yearly IPCA data series. These data are provided as part of this replication package. The data file must be stored in ~/inputs/cpi/IPCA_IPEA_13February2019.xls.

--- The minimum-wage data from Instituto de Pesquisa Econômica Aplicada (2020) come in Microsoft Excel-native .xls format. The raw data contain two variables or columns: The first column "Data" is the year and month in YYYY.MM format, while the second column "Salário mínimo - R$ - Ministério do Trabalho e Emprego (MTE) - MTE12_SALMIN12 -". The cleaning routines in ~/code/cleaning_rais process this raw .xls file and produce two Stata-native .dta files: mw_bra.dta for a monthly minimum-wage data series and mw_bra_yearly.dta for a yearly minimum-wage data series. These data are provided as part of this replication package. The data file must be stored in ~/inputs/mw/minwage_nominal_IPEA_13February2019.xls.

--- The industry code crosswalks and occupation code crosswalks from Engbom and Moser (2022b) come in Stata-native .dta format. Each file is stored in its own location and contains its own set of variables or columns:
      --- ~/inputs/ind/ind07_5_to_ind95_5_official.dta: The first column "ind07_5" is the 2007 5-digit Brazilian industry code and the second column "ind95_5" is the 1995 5-digit  Brazilian industry code.
      --- ~/inputs/ind/ind85_2_to_ind95_5_official.dta: The first column "ind85_2" is the 1985 2-digit Brazilian industry code and the second column "ind95_5" is the 1995 5-digit  Brazilian industry code.
      --- ~/inputs/ind/ind07_5_to_ind95_5_official.dta: The first column "ind95_5" is the 1995 5-digit Brazilian industry code and the second column "ind07_5" is the 2007 5-digit  Brazilian industry code.
      --- ~/inputs/ind/ind07_5_to_ind95_5_official.dta: The first column "ind95_5" is the 1995 5-digit Brazilian industry code and the second column "ind85_2" is the 1985 2-digit  Brazilian industry code.
      --- ~/inputs/occ/occ_bra_to_occ_us.dta: The first column "occ94_5" is the 1994 5-digit Brazilian occupation code, the second column "occ94_5_desc" is the 1994 5-digit Brazilian occupation description, the third column "occ90_us" is the 1990 US Census occupation code, and the fourth column "occ90_us_desc" is the 1990 US Census occupation description.
      --- ~/inputs/occ/occ_us_to_skill_tasks_contents.dta: The first column "occ90_us" is the 1990 US Census occupation code, the second column "occ90_us_desc" is the 1990 US Census occupation description, and columns 3-14 are the standardized skill and task contents corresponding to each US Census occupation code.
      --- ~/inputs/occ/occ02_6_to_occ94_5_official.dta: The first column "occ02_6" is the 2002 6-digit Brazilian occupation code and the second column "occ94_5" is the 1994 5-digit Brazilian occupation code.
      --- ~/inputs/occ/occ94_5_to_occ02_6_official.dta: The first column "occ94_5" is the 1994 5-digit Brazilian occupation code and the second column "occ02_6" is the 2002 6-digit Brazilian occupation code.

--- The exchange-rates data from International Monetary Fund (2022) come in Microsoft Excel-native .xls format. The raw data contain three variables or columns: The first column "year" is the calendar year, the second column "fx_usdArgentina" is the United States's USD exchange rate with respect to Argentina's ARS, and the third column "fx_usdBrazil" is the United States's USD exchange rate with respect to Brazil's BRL. These data are provided as part of this replication package. The data file must be stored in ~/inputs/fx/fx_data.xls.

--- The Orbis Historical data from Moody’s Analytics (2025) come in compressed .rar format. The cleaning routines in ~/code/cleaning_orbis will automatically extract the raw data files and store them in Stata-native .dta format. These cleaning routines also contain a data dictionary in English, which is used to name and label all variables. These data are not provided as part of this replication package. The data files must be stored in ~/inputs/orbis. The raw data are characterized by the following codebook:
      --- bvdidnumber (string)
      --- closingdate (numeric)
      --- consolidationcode (string)
      --- operatingrevenueturnover (numeric)
      --- plbeforetax (numeric)
      --- plforperiodnetincome (numeric)
      --- cashflow (numeric)
      --- totalassets (numeric)
      --- shareholdersfunds (numeric)
      --- marketcapitalisationmil (numeric)
      --- numberofmonths (numeric)
      --- originalcurrency (string)
      --- exchangeratefromoriginalcurren (numeric)
      --- originalunits (string)
      --- filingtype (string)

--- The MATLAB inputs, consisting of initial guesses and precomputed results, from Morchio and Moser (2025) come in MATLAB-native .mat format. These data are read in by the model codes in ~/code/model, which are automatically called as part of the replication package's third main file (~/code/data/MM_0_MASTER.do). The input files must be stored in ~/inputs/matlab.

--- Code for data cleaning and analysis is provided as part of the replication package. It is available at https://www.dropbox.com/scl/fo/njgiuebx15ufng815va8f/AHCZrcxmebOX4L8RaCHmyps?rlkey=9ui4r4dm7o5opyic31hjzu2xm&dl=0 for review. It will be uploaded to the AER repository (OpenICPSR) once the paper has been conditionally accepted.

--- See the section "Inputs Folder" below for a list of all (sub-)folders and file names, including descriptions.


# ------------
# DATASET LIST
# ------------

--- Datasets used by codes in the folder ~/code/cleaning_rais:
      --- Raw version of the RAIS from Ministério da Economia (2022): confidential and not provided as part of this replication package.
      --- IPCA from Instituto de Pesquisa Econômica Aplicada (2019): public and provided as part of this replication package. The relevant consumer price index time series are included as part of the replication package and stored at ~/inputs/cpi.
      --- Minimum wage from Instituto de Pesquisa Econômica Aplicada (2020): public and provided as part of this replication package.
      --- Industry code crosswalks and occupation code crosswalks from Engbom and Moser (2022b): public and provided as part of this replication package.

--- Datasets used by codes in the folder ~/code/cleaning_orbis:
      --- Raw version of the Orbis Historical data from Moody’s Analytics (2025): proprietary and not provided as part of this replication package.
      --- Exchange rates from BRL and ARS to USD from International Monetary Fund (2022): public and provided as part of this replication package.
 
--- Datasets used by codes in the folder ~/code/data:
      --- Processed version of the RAIS, which was created using the codes in the folder ~/code/cleaning_rais, based on the raw version of the RAIS data from Ministério da Economia (2022): confidential and not provided as part of this replication package.
      --- Processed version of the Orbis Historical, which was created using the codes in the folder ~/code/cleaning_orbis, based on the raw version of the Orbis Historical data from Moody's Analytics (2025): proprietary and not provided as part of this replication package.

--- Datasets used by codes in the folder ~/code/model:
      --- MATLAB inputs, consisting of initial guesses and precomputed results, from Morchio and Moser (2025).

--- See the section "Inputs Folder" below for a list of all (sub-)directories and file names, including descriptions.


# --------------------------
# COMPUTATIONAL REQUIREMENTS
# --------------------------

--- All analyses (i.e., empirical analyses using Stata and MATLAB and model analyses using MATLAB) were run on a server with Debian GNU/Linux 10 (buster) with 1024GB RAM (DDR5 4800MT/s 64GB DIMM CL40 P/N MTC40F2046S1RC48BA1), 1 core (AMD 9354 32c 3.25GHz 256MB L3 cache), and 1.5TB disk space.
      --- Although many of the routines can be parallelized across more than 1 core for additional speed gains, exact replicability up to machine precision requires running all routines on a single core.

--- Software requirements:
      --- Stata/MP version 18.0, including the following packages:
            --- binscatter (https://ideas.repec.org/c/boc/bocode/s457709.html, as of November 24, 2013)
            --- carryforward (https://ideas.repec.org/c/boc/bocode/s444902.html, as of February 12, 2016)
            --- chunky (https://ideas.repec.org/c/boc/bocode/s456994.html, as of September 1, 2010)
            --- confirmdir (https://ideas.repec.org/c/boc/bocode/s435507.html, as of February 26, 2011)
            --- egenmore (https://ideas.repec.org/c/boc/bocode/s386401.html, as of January 24, 2019)
            --- moremata (https://ideas.repec.org/c/boc/bocode/s455001.html, as of February 19, 2022)
            --- ftools (https://ideas.repec.org/c/boc/bocode/s458213.html, as of August 21, 2023)
            --- gtools (https://ideas.repec.org/c/boc/bocode/s458514.html, as of December 5, 2022)
            --- reghdfe (https://ideas.repec.org/c/boc/bocode/s457874.html, as of August 21, 2023)
            --- All required Stata packages are included as part of the replication package inside the subdirectories ~/code/cleaning_rais/_stata_packages, ~/code/cleaning_orbis/_stata_packages, and ~/code/data/_stata_packages.
      --- MATLAB R2023a Update 5 (9.14.0.2337262) 64-bit (glnxa64), including the following toolboxes:
            --- Optimization Toolbox (https://www.mathworks.com/products/optimization.html, as of August 19, 2025)
            --- Statistics and Machine Learning Toolbox (https://www.mathworks.com/products/statistics.html, as of August 19, 2025)
            --- Parallel Computing Toolbox (https://www.mathworks.com/products/parallel-computing.html, as of August 19, 2025)
            --- The required MATLAB packages are not included as part of the replication package but can be obtained as part of the standard MATLAB installation.
      --- 7-Zip 21.02 alpha for Linux and macOS (2021-05-06):
            --- This file archiver software is publicly available under a GNU LGPL license (https://www.7-zip.org/, as of August 19, 2025) and included as part of the replication package inside the subdirectory ~/code/cleaning_rais/_7z.
      --- Parts of the code use bash or zsh scripting, which may require Unix. The exact versions used are GNU bash, version 5.0.3(1)-release (x86_64-pc-linux-gnu) or zsh 5.7.1 (x86_64-debian-linux-gnu).
      --- Parts of the code call MATLAB from within Stata, which may cause difficulties with calling MATLAB from shell and instructing Stata to wait for results when executed on some operating systems.

--- Controlled randomness:
      --- The master code files "RAIS_0_MASTER.do," "ORBIS_0_MASTER.do," and "MM_0_MASTER.do" use the Stata commands -set seed- and -set sortseed- in order to set a specific value for the random-number seed and the sort seed in Stata. These seeds ensure that any computations involving randomness, including simulated variable values and sort orders, are exactly replicable when run by a third party.
      --- The code files "MM_AKM_KSS.m," "MM_AKM.m," "MM_CONNECTED_LOO.m," "MM_CONNECTED.m," and "MM_PAGERANKS.m" inside ~/code/data, the code files "do_estimation_men.m," "do_estimation_women.m," "do_read_parameters.m," and "do_robustness.m" inside ~/code/model/solution, and the code files "do_counterfactuals.m," "do_simulations.m," "fun_model_GG.m," "fun_montecarlo_DGP.m," "fun_montecarlo_table.m," and "fun_simulate_model.m" inside ~/code/model/solution use the commands -rng()- in order to set a random-number seed in MATLAB. These seeds ensure that any computations involving randomness, including simulated variable values, are exactly replicable when run by a third party.

--- Memory, runtime, and storage requirements:
      --- The memory requirement is up to 1024GB RAM at peak load.
      --- The total runtime is approximately 42 days:
            --- 34 days for part 1, cleaning the RAIS data
            --- 1 day for part 2, cleaning the Orbis Historical data
            --- 7 days for part 3, running all analyses and producing all exhibits contained in Morchio and Moser (2025)
      --- Storage disk space of at least 1.5TB is recommended.


# -------------------------------------------
# DESCRIPTION OF REPLICATION CODES AND INPUTS
# -------------------------------------------

--- The following subsections describe in detail the replication codes and inputs inside the following folders of the replication package:
      --- ~/code/cleaning_rais
      --- ~/code/cleaning_orbis
      --- ~/code/data
      --- ~/code/model
            --- ~/code/model/estimation
            --- ~/code/model/solution
      --- ~/inputs


## --------------------------------------------
## REPLICATION CODE FOLDER ~/code/cleaning_rais
## --------------------------------------------

--- Contains Stata .do files that read the raw RAIS data and produce a set of cleaned data files separately for each year 1985-2018.

--- The list of included code files is as follows:
      --- RAIS_0_MASTER.do: Master file that runs all other files.
      --- RAIS_1_READ.do: Reads the raw RAIS data by calling a sequence of other files and saves read files.
            --- RAIS_1A_READ_UNZIP.do: Unzips the compressed raw data.
            --- RAIS_1B_READ_ACCENTS.do: Converts accents into readable format.
            --- RAIS_1C_READ_RENAME.do: Renames key variables.
            --- RAIS_1D_READ_DESTRING.do: Destrings variables appropriately.
            --- RAIS_1E_READ_LABEL.do: Labels key variables.
      --- RAIS_2_CLEAN.do: Cleans data based on the complete set of read files for 1985-2018.
            --- RAIS_2A_CONVERSION: Creates conversion datasets for the minimum wage and the IPCA

--- The final output from this procedure is a set of files ~/inputs/rais/rais1985.dta, ~/inputs/rais/rais1986.dta, ..., ~/inputs/rais/rais2018.dta, each of which contains the cleaned RAIS data for a given year in the range 1985-2018. These files are required in order to run the empirical analysis in Morchio and Moser (2025).


### ------------------------------------------------
### REPLICATION CODE FOLDER ~/code/cleaning_rais/_7z
### ------------------------------------------------

--- This folder contains the 7-Zip file archiver software for Windows, Linux, and macOS. This software is called in line 39 of ~/code/cleaning_rais/RAIS_1A_READ_UNZIP.do.


### ------------------------------------------------------------
### REPLICATION CODE FOLDER ~/code/cleaning_rais/_stata_packages
### ------------------------------------------------------------

--- This folder contains all the packages required for the execution of the Stata codes in ~/code/cleaning_rais. These packages comprise:
      --- egenmore
      --- ftools
      --- gtools


## ---------------------------------------------
## REPLICATION CODE FOLDER ~/code/cleaning_orbis
## ---------------------------------------------

--- Contains Stata .do files that read the raw Orbis Historical data and produce a cleaned data file.

--- The list of included code files is as follows:
      --- ORBIS_0_MASTER.do: Master file that defines settings and runs the next file.
      --- ORBIS_1_MERGE.do: Reads the raw Orbis Historical data for Brazilian reporting entities and merges them into the universe of firms and establishments captured by the RAIS data.

--- The final output from this procedure is a file ~/inputs/orbis/bvd_orbis_historical_bra.dta that contains the processed Orbis Historical data for Brazilian establishments and firms captured by the RAIS data. This file is required in order to run the empirical analysis following the model estimation in ~/code/data/MM_14_ANALYSIS_DATA.do, which relates model estimates of productivity to measures of firm productivity in the data.

--- Note that the third main file (~/code/data/MM_0_MASTER.do) has a global macro sim_orbis that can be set to = 0 if working with the proprietary Orbis Historical data or set to = 1 if working with the simulated version of the Orbis Historical data (~/inputs/orbis/bvd_orbis_historical_bra_sim.dta) that is included as part of this replication package. This simulated file comes as part of the replication package but a substantially identical version (up to the random seed) is created in lines 524-549 of ~/code/data/MM_14_ANALYSIS_DATA.do whenever the global macro sim_orbis = 0 in the third main file (~/code/data/MM_0_MASTER.do).


### -------------------------------------------------------------
### REPLICATION CODE FOLDER ~/code/cleaning_orbis/_stata_packages
### -------------------------------------------------------------

--- This folder contains all the packages required for the execution of the Stata codes in ~/code/cleaning_orbis. These packages comprise:
      --- chunky
      --- egenmore
      --- ftools
      --- gtools


## -----------------------------------
## REPLICATION CODE FOLDER ~/code/data
## -----------------------------------

--- Contains Stata .do files that read the processed RAIS data and produce a set of cleaned data files separately for each year 2007-2014.

--- The list of included code files is as follows:
      --- MM_0_MASTER.do: Master file that runs all other files
      --- MM_1_SELECTION.do: Starts with raw data and imposes selection criteria
      --- MM_2_CONNECTED.do: Finds employer IDs and job IDs in connected set
      --- MM_3_AKM.do: Estimates AKM model to find gender-specific firm pay components
      --- MM_4_RANKS.do: Computes firm-level revealed-preference indices and ranks
      --- MM_5_LAB_PARAMS.do: Computes labor market "parameters" based on monthly panel data including employer ranks
      --- MM_6_ESTIMATION.do: Prepares data for the estimation of the structural model
      --- MM_7_FIRM_PARAMETERS.do: Estimates the firm-specific productivity (p), amenities (pi_g) and gender wedges (z). This also outputs the following:
            --- ~/paper/tables/tab_economy_wide_parameters_rank5.tex: the table with baseline estimates of economy-wide parameters (Table 8 in Section 6 of the main text)
      --- MM_8_POST_EST.do: Creates files for post-estimation analysis
      --- MM_9_COVARIATES.do: Computes employer-level covariates of amenities, productivities, and gender wedges
      --- MM_10_PROJECTIONS.do: Projects estimates of gender-specific amenities and gender wedges onto observables
      --- MM_11_SUM_STATS.do: Produces summary statistics by gender
      --- MM_12_GAPS.do: Estimates gender pay gaps within and between employers
      --- MM_13_ANALYSIS_MODEL.do: Further model analysis, which outputs the following:
            --- ~/paper/tables/tab_R1_pagerank.tex: The table which compares baseline estimates to those obtained by using PageRank to rank firms instead of firm size (Table E.3 in Supplemental Appendix E)
            --- ~/paper/tables/tab_R2_hetdelta.tex: The table which compares baseline estimates to those that allow for heterogeneous separation rates across firms (Table E.5 in Supplemental Appendix E)
            --- ~/paper/tables/tab_R2_eta_a_robustness.tex: The table with comparisons across estimations that target different values of the cost share of amenities (Table E.7 in Supplemental Appendix E)
      --- MM_14_ANALYSIS_DATA.do: Further data analysis, which outputs the following figures, table, and text snippet:
            --- ~/paper/figures/fig_fit_pay.eps: Model fit in terms of pay (Panel A of Figure 2 in Section 6 of the main text)
            --- ~/paper/figures/fig_fit_size.eps: Model fit in terms of size (Panel B of Figure 2 in Section 6 of the main text)
            --- ~/paper/figures/fig_model_fit_w_size_m.eps: Model fit in terms of mean log pay against log industry size, men (Panel A of Figure E.6 in Supplemental Appendix E)
            --- ~/paper/figures/fig_model_fit_w_size_f.eps: Model fit in terms of mean log pay against log industry size, women (Panel B of Figure E.6 in Supplemental Appendix E)
            --- ~/paper/figures/compare_pagerank_size_1.eps: Comparing alternative employer rank measures across sectors, PageRank vs size, men (Panel A of Figure E.7 in Supplemental Appendix E)
            --- ~/paper/figures/compare_pagerank_size_2.eps: Comparing alternative employer rank measures across sectors, PageRank vs size, women (Panel B of Figure E.7 in Supplemental Appendix E)
            --- ~/paper/figures/compare_poaching_size_1.eps: Comparing alternative employer rank measures across sectors, Poaching rank vs size, men (Panel C of Figure E.7 in Supplemental Appendix E)
            --- ~/paper/figures/compare_poaching_size_2.eps: Comparing alternative employer rank measures across sectors, Poaching rank vs size, women (Panel D of Figure E.7 in Supplemental Appendix E)
            --- ~/paper/figures/fig_public_share_ladder_m.eps: Share of employment in public sector across firm ranks, men (Panel A of Figure F.2 in Supplemental Appendix F)
            --- ~/paper/figures/fig_public_share_ladder_f.eps: Share of employment in public sector across firm ranks, women (Panel B of Figure F.2 in Supplemental Appendix F)
            --- ~/paper/figures/fig_corr_dem_rank_gender_edu_m.eps: Binscatter plots of employer ranks across population subgroups, Low education vs. high education, men (Panel A of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/figures/fig_corr_dem_rank_gender_edu_f.eps: Binscatter plots of employer ranks across population subgroups, Low education vs. high education, women (Panel B of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/figures/fig_corr_dem_rank_gender_parent_m.eps: Binscatter plots of employer ranks across population subgroups, Parents vs. nonparents, men (Panel C of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/figures/fig_corr_dem_rank_gender_parent_f.eps: Binscatter plots of employer ranks across population subgroups, Parents vs. nonparents, women (Panel D of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/figures/fig_corr_dem_rank_gender_yob_m.eps: Binscatter plots of employer ranks across population subgroups, Young cohorts vs. old cohort, men (Panel E of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/figures/fig_corr_dem_rank_gender_yob_f.eps: Binscatter plots of employer ranks across population subgroups, Young cohorts vs. old cohort, women (Panel F of Figure D.3 in Supplemental Appendix D)
            --- ~/paper/tables/tab_reg_productivity.tex: Regressing empirical productivity measures on model estimates of firm productivity (Table 5 in Section 6 of the main text) -- note: this table will be based on simulated Orbis Historical data whenever the global macro sim_orbis = 1, which will result in numbers different from the published version of this table based on the proprietary Orbis Historical data that is used whenever the global macro sim_orbis = 0 in the third main file (~/code/data/MM_0_MASTER.do)
            --- ~/paper/text/txt_financials_b_log_revenue_pw_data.tex
      --- MM_15_FIGURES.do: Produces the following figures for the paper:
            --- ~/paper/figures/fig_densities_baseline.eps (Panel A of Figure 1 in Section 3 of the main text)
            --- ~/paper/figures/fig_appendix_densities_alt_1.eps  Decomposition 1: Between-gap, men's FEs (Panel A of Figure B.7 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_densities_alt_2.eps: Decomposition 2: Between-gap, women's FEs (Panel C of Figure B.7 in Supplemental Appendix B)
            --- ~/paper/figures/fig_within_baseline.eps (Panel B of Figure 1 in Section 3 of the main text)
            --- ~/paper/figures/fig_appendix_within_alt_1.eps: Decomposition 2: Within-gap, men's weights (Panel D of Figure B.7 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_within_alt_2.eps: Decomposition 1: Within-gap, women's weights (Panel B of Figure B.7 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_hours.eps: Predicted AKM contractual work hours FEs, by gender (Figure B.1 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_occ.eps: Predicted AKM occupation FEs, by gender (Figure B.2 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_exp_act.eps: Predicted AKM actual-experience FEs, by gender (Figure B.3 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_xb_tenure.eps: Predicted AKM tenure FEs, by gender (Figure B.4 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_xb_year_m.eps: Predicted AKM education-year FEs, men (Panel A of Figure B.5 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_xb_year_f.eps: Predicted AKM education-year FEs, women (Panel B of Figure B.5 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_xb_age_m.eps: Predicted AKM education-age FEs, men (Panel A of Figure B.6 in Supplemental Appendix B)
            --- ~/paper/figures/fig_appendix_akm_xb_age_f.eps: Predicted AKM education-age FEs, women (Panel B of Figure B.6 in Supplemental Appendix B)
            --- ~/paper/figures/fig_kdens_ranks.eps: Employment-weighted density of employer ranks, by gender (Figure E.1 in Supplemental Appendix E)
            --- ~/paper/figures/fig_recruiting_unw.eps: Density estimates of recruiting intensities, by gender, unweighted (Panel A of Figure E.2 in Supplemental Appendix E)
            --- ~/paper/figures/fig_recruiting_w.eps: Density estimates of recruiting intensities, by gender, Employment-weighted (Panel B of Figure E.2 in Supplemental Appendix E)
            --- ~/paper/figures/fig_productivity_unw.eps: Density of log estimated productivity, by gender, unweighted (Panel A of Figure E.3 in Supplemental Appendix E)
            --- ~/paper/figures/fig_productivity_w.eps: Density of log estimated productivity, by gender, weighted (Panel B of Figure E.3 in Supplemental Appendix E)
            --- ~/paper/figures/fig_gender_wedge_unw.eps: Density of estimated gender wedges, by gender, unweighted (Panel A of Figure E.4 in Supplemental Appendix E)
            --- ~/paper/figures/fig_gender_wedge_w.eps: Density of estimated gender wedges, by gender, weighted (Panel B of Figure E.4 in Supplemental Appendix E)
            --- ~/paper/figures/fig_amenity_cost_shifters_unw.eps: Densities of log amenity cost shifters, by gender, unweighted (Panel A of Figure E.5 in Supplemental Appendix E)
            --- ~/paper/figures/fig_amenity_cost_shifters_w.eps Densities of log amenity cost shifters, by gender, weighted (Panel B of Figure E.5 in Supplemental Appendix E)
            --- ~/paper/figures/fig_wage_dist.eps: Estimated distributions of pay, by gender (Panel A of Figure 5 in Section 7 of the main text)
            --- ~/paper/figures/fig_amenity_dist.eps: Estimated distributions of amenity valuations, by gender (Panel B of Figure 5 in Section 7 of the main text)
            --- ~/paper/figures/fig_ind_ranks_x_w_m.eps: Sectoral employer ranks against employer pay ranks, men (Panel A of Figure 3 in Section 7 of the main text)
            --- ~/paper/figures/fig_ind_ranks_x_w_f.eps: Sectoral employer ranks against employer pay ranks, women (Panel B of Figure 3 in Section 7 of the main text)
            --- ~/paper/figures/fig_ind_ranks_x_a_m.eps: Sectoral employer ranks against employer amenity ranks, men (Panel A of Figure 4 in Section 7 of the main text)
            --- ~/paper/figures/fig_ind_ranks_x_a_f.eps: Sectoral employer ranks against employer amenity ranks, women (Panel B of Figure 4 in Section 7 of the main text)
            --- ~/paper/figures/fig_dist_amenity_shares.eps: Distribution of amenity shares, by gender (Panel A of Figure 7 in Section 7 of the main text)
            --- ~/paper/figures/fig_amenity_shares_ranks.eps: Amenity shares across ranks, by gender (Panel B of Figure 7 in Section 7 of the main text)
            --- ~/paper/figures/fig_prod_ranks.eps: Productivity across ranks, by gender (Panel A of Figure F.3 in Supplemental Appendix F)
            --- ~/paper/figures/fig_log_p_f_log_p_m.eps: Incidence of gender wedges (Panel B of Figure F.3 in Supplemental Appendix F)
            --- ~/paper/figures/fig_comp_ladder_m.eps: Pay, amenity valuations, and total compensation across employer ranks, men (Panel A of Figure 6 in Section 7 of the main text)
            --- ~/paper/figures/fig_comp_ladder_f.eps: Pay, amenity valuations, and total compensation across employer ranks, women (Panel B of Figure 6 in Section 7 of the main text)
            --- ~/paper/figures/fig_appendix_exp_act_vs_exp_pot_m.eps: Percentiles of actual experience conditional on potential experience, men (Panel A of Figure A.1 in Supplemental Appendix A)
            --- ~/paper/figures/fig_appendix_exp_act_vs_exp_pot_f.eps: Percentiles of actual experience conditional on potential experience, women (Panel B of Figure A.1 in Supplemental Appendix A)
            --- ~/paper/figures/fig_women_to_men_x.eps: Outcomes associated with moving men into women’s employers and vice versa; Women: Total compensation (Panel F of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_women_to_men_pi.eps: Outcomes associated with moving men into women’s employers and vice versa; Women: Amenities (Panel E of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_women_to_men_w.eps: Outcomes associated with moving men into women’s employers and vice versa; Women: Pay (Panel D of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_men_to_women_x.eps: Outcomes associated with moving men into women’s employers and vice versa; Men: Total compensation (Panel C of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_men_to_women_pi.eps: Outcomes associated with moving men into women’s employers and vice versa; Men: Amenities (Panel B of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_men_to_women_w.eps: Outcomes associated with moving men into women’s employers and vice versa; Men: Pay (Panel A of Figure F.4 in Supplemental Appendix F)
            --- ~/paper/figures/fig_amenities_wedges.eps: Negative relation between women’s amenities and gender wedges (Figure F.1 in Supplemental Appendix F)
      --- MM_16_TABLES.do: Produces the following tables for the paper:
            --- ~/paper/tables/tab_sum_stats.tex: Summary statistics table (Table 1 in Section 2 of the main text)
            --- ~/paper/tables/tab_akm_combined_decomp.tex: Variance decompositions based on plug-in and leave-out estimates (Table 2 in Section 3 of the main text)
            --- ~/paper/tables/tab_kob_log_w.tex: Alternative Kitagawa-Oaxaca-Blinder decompositions of the gender log pay gap (Table B.1 in Supplemental Appendix B)
            --- ~/paper/tables/tab_kob_log_w_short.tex: KOB decomposition (Table 3 in Section 3 of the main text)
            --- ~/paper/tables/tab_kob_log_pi_tilde.tex: Alternative Kitagawa-Oaxaca-Blinder decompositions of the gender gap in amenities (Table F.1 in Supplemental Appendix F)
            --- ~/paper/tables/tab_kob_log_x.tex: Alternative Kitagawa-Oaxaca-Blinder decompositions of the gender gap in utility (Table F.2 in Supplemental Appendix F)
            --- ~/paper/tables/tab_kob_log_w_pi_x.tex: Kitagawa-Oaxaca-Blinder decompositions of gaps in pay, amenity valuations, and total compensation (Table 11 in Section 7 of the main text)
            --- ~/paper/tables/tab_kob_log_w_pi_x_pri.tex: Kitagawa-Oaxaca-Blinder decompositions—private sector only (Table F.3 in Supplemental Appendix F)
            --- ~/paper/tables/tab_kob_log_w_pi_x_pub.tex: Kitagawa-Oaxaca-Blinder decompositions—public sector only (Table F.4 in Supplemental Appendix F)
            --- ~/paper/tables/tab_kob_log_w_pi_x_eta_a_h.tex: Kitagawa-Oaxaca-Blinder decompositions—half baseline’s amenity share target (Table E.8 in Supplemental Appendix E)
            --- ~/paper/tables/tab_kob_log_w_pi_x_eta_a_d.tex: Kitagawa-Oaxaca-Blinder decompositions—double baseline’s amenity share target (Table E.9 in Supplemental Appendix E)
            --- ~/paper/tables/tab_kob_log_w_pi_x_delta.tex: Kitagawa-Oaxaca-Blinder decompositions—heterogeneous firm-level separation rates (Table E.6 in Supplemental Appendix E)
            --- ~/paper/tables/tab_kob_log_w_pi_x_pageranks.tex: Kitagawa-Oaxaca-Blinder decompositions—alternative employer ranks based on PageRanks (Table E.4 in Supplemental Appendix E)
            --- ~/paper/tables/tab_lab_params.tex: Estimated labor market parameters (Table 4 in Section 6 of the main text)
            --- ~/paper/tables/tab_corr_m.tex: Correlation table for estimated employer parameters, men (Panel A of Table E.1 in Supplemental Appendix E)
            --- ~/paper/tables/tab_corr_f.tex: Correlation table for estimated employer parameters, women (Panel B of Table E.1 in Supplemental Appendix E)
            --- ~/paper/tables/tab_corr_cross.tex: Correlation table for estimated employer parameters, cross-gender (Panel C of Table E.1 in Supplemental Appendix E)
            --- ~/paper/tables/tab_appendix_a1.tex: Summary statistics for the raw data (Table A.1 in Supplemental Appendix A)
            --- ~/paper/tables/tab_appendix_a2.tex: Summary statistics for selected sample (Table A.2 in Supplemental Appendix A)
            --- ~/paper/tables/tab_appendix_a3.tex: Summary statistics for connected set (Table A.3 in Supplemental Appendix A)
            --- ~/paper/tables/tab_appendix_a4.tex: Comparison of summary statistics (selection vs. all) (Table A.4 in Supplemental Appendix A)
            --- ~/paper/tables/tab_appendix_a5.tex Comparison of summary statistics (connected vs. selection) (Table A.5 in Supplemental Appendix A)
            --- ~/paper/tables/tab_reg_amenities.tex: Regressing estimates of amenity valuations on employer characteristics, by gender (Table 7 in Section 6 of the main text)
            --- ~/paper/tables/tab_reg_wedges.tex: Regressing estimates of transformed gender wedges on employer characteristics (Table 6 in Section 6 of the main text)
            --- ~/paper/tables/tab_var_pay_decomp.tex: Decomposition of employer pay dispersion into utility and amenity terms (Table 10 in Section 7 of the main text)
            --- ~/paper/tables/tab_ranks.tex: Rank correlations between alternative employer rank measures, by gender (Table E.2 in Supplemental Appendix E)
      --- MM_17_TEXT.do: Produces the following text snippets for the paper:
            --- ~/paper/text/txt_model_rho.tex
            --- ~/paper/text/txt_model_discount_rate.tex
            --- ~/paper/text/txt_model_alpha.tex
            --- ~/paper/text/txt_model_chi.tex
            --- ~/paper/text/txt_pop_share_m.tex
            --- ~/paper/text/txt_pop_share_f.tex
            --- ~/paper/text/txt_delta_m.tex
            --- ~/paper/text/txt_delta_f.tex
            --- ~/paper/text/txt_lambda_u_m.tex
            --- ~/paper/text/txt_lambda_u_f.tex
            --- ~/paper/text/txt_lambda_e_m.tex
            --- ~/paper/text/txt_lambda_e_f.tex
            --- ~/paper/text/txt_lambda_g_m.tex
            --- ~/paper/text/txt_lambda_g_f.tex
            --- ~/paper/text/txt_b_m.tex
            --- ~/paper/text/txt_b_f.tex
            --- ~/paper/text/txt_phi_m.tex
            --- ~/paper/text/txt_phi_f.tex
            --- ~/paper/text/txt_u_m.tex
            --- ~/paper/text/txt_u_f.tex
            --- ~/paper/text/txt_akm_var_m.tex
            --- ~/paper/text/txt_akm_var_f.tex
            --- ~/paper/text/txt_akm_var_pers_fe_sh_m.tex
            --- ~/paper/text/txt_akm_var_pers_fe_sh_f.tex
            --- ~/paper/text/txt_akm_var_emp_fe_sh_m.tex
            --- ~/paper/text/txt_akm_var_emp_fe_sh_f.tex
            --- ~/paper/text/txt_akm_corr_pers_emp_m.tex
            --- ~/paper/text/txt_akm_corr_pers_emp_f.tex
            --- ~/paper/text/txt_akm_r2.tex
            --- ~/paper/text/txt_akm_mean_fe_m.tex
            --- ~/paper/text/txt_akm_kss_var_y_1.tex
            --- ~/paper/text/txt_akm_kss_var_y_2.tex
            --- ~/paper/text/txt_akm_kss_corr_fe_pe_leaveout_1.tex
            --- ~/paper/text/txt_akm_kss_r_2_leaveout_1.tex
            --- ~/paper/text/txt_akm_kss_corr_fe_pe_leaveout_2.tex
            --- ~/paper/text/txt_akm_kss_share_var_fe_leaveout_1.tex
            --- ~/paper/text/txt_akm_kss_share_var_pe_leaveout_1.tex
            --- ~/paper/text/txt_akm_kss_share_var_fe_leaveout_2.tex
            --- ~/paper/text/txt_akm_kss_share_var_pe_leaveout_2.tex
            --- ~/paper/text/txt_kob_gender_gap_log_w.tex
            --- ~/paper/text/txt_kob_share_between_1_log_w.tex
            --- ~/paper/text/txt_kob_level_between_1_log_pi_tilde.tex
            --- ~/paper/text/txt_kob_level_within_1_log_w.tex
            --- ~/paper/text/txt_kob_level_within_1_log_pi_tilde.tex
            --- ~/paper/text/txt_kob_bargaining_disadvantage.tex
            --- ~/paper/text/txt_sum_stats_n_worker_years.tex
            --- ~/paper/text/txt_sum_stats_n_workers.tex
            --- ~/paper/text/txt_sum_stats_n_estab.tex
            --- ~/paper/text/txt_sum_stats_sh_f.tex
            --- ~/paper/text/txt_sum_stats_gap_share_fe_earn.tex
            --- ~/paper/text/txt_sum_stats_earn_gap.tex 
            --- ~/paper/text/txt_mean_log_pi_m.tex
            --- ~/paper/text/txt_mean_log_pi_f.tex
            --- ~/paper/text/txt_pi_share_m_mean.tex
            --- ~/paper/text/txt_pi_share_f_mean.tex
            --- ~/paper/text/txt_gap_log_w.tex
            --- ~/paper/text/txt_gap_log_pi.tex
            --- ~/paper/text/txt_gap_log_pi_tilde.tex
            --- ~/paper/text/txt_gap_log_x.tex
            --- ~/paper/text/txt_var_log_w_m.tex
            --- ~/paper/text/txt_var_log_w_f.tex
            --- ~/paper/text/txt_var_log_x_m.tex
            --- ~/paper/text/txt_var_log_x_f.tex
            --- ~/paper/text/txt_gap_log_x_share.tex
            --- ~/paper/text/txt_var_x_share_m.tex
            --- ~/paper/text/txt_var_x_share_f.tex
            --- ~/paper/text/txt_elast_m.tex
            --- ~/paper/text/txt_elast_f.tex
            --- ~/paper/text/txt_cf1_change_log_w_f.tex
            --- ~/paper/text/txt_cf1_change_log_pi_f_minus_m.tex
            --- ~/paper/text/txt_cf1_change_log_x_f_minus_m.tex
            --- ~/paper/text/txt_cf1_change_log_w_m_minus_f.tex
            --- ~/paper/text/txt_cf1_change_log_pi_m.tex
            --- ~/paper/text/txt_cf1_change_log_x_m_minus_f.tex
            --- ~/paper/text/txt_cf2_change_log_w_f.tex
            --- ~/paper/text/txt_cf2_change_log_pi_f.tex
            --- ~/paper/text/txt_cf2_change_log_x_f.tex
            --- ~/paper/text/txt_cf2b_change_log_w_m_minus_f.tex
            --- ~/paper/text/txt_cf2b_change_log_pi_m_minus_f.tex
            --- ~/paper/text/txt_cf2b_change_log_x_m_minus_f.tex
            --- ~/paper/text/txt_reg_amenities_r2_men.tex
            --- ~/paper/text/txt_reg_amenities_r2_women.tex
            --- ~/paper/text/txt_reg_wedges_r2.tex
            --- ~/paper/text/txt_N_ind07_5.tex
            --- ~/paper/text/txt_N_muni.tex
            --- ~/paper/text/txt_N_occ02_6.tex
            --- ~/paper/text/txt_N_ind85_2.tex
            --- ~/paper/text/txt_mean_rank_m.tex
            --- ~/paper/text/txt_mean_rank_f.tex
            --- ~/paper/text/txt_mean_log_prod_m.tex
            --- ~/paper/text/txt_mean_log_prod_f.tex
            --- ~/paper/text/txt_mean_log_prod_gap.tex
            --- ~/paper/text/txt_tau_m_mean.tex
            --- ~/paper/text/txt_tau_f_mean.tex
            --- ~/paper/text/txt_corr_log_w.tex
            --- ~/paper/text/txt_corr_log_pi.tex
            --- ~/paper/text/txt_corr_rank.tex
            --- ~/paper/text/txt_log_x_m_range.tex
            --- ~/paper/text/txt_log_x_f_range.tex
      --- MM_18_SIMULATIONS.do: Runs all model counterfactuals and Monte Carlo simulations, which outputs the following table, figures, and text snippets:
            --- ~/paper/tables/tab_montecarlo_100000.tex: Monte Carlo simulation and estimation on 100,000 firms (Table D.1 in Supplemental Appendix D)
            --- ~/paper/figures/fig_MC_scatter_ahat_vs_a_FOCs_100000_x.eps: Amenity estimates against true amenities in Monte Carlo simulations (all subfigures (for simulation x=1..5) of Figure D.1 in Supplemental Appendix D)
            --- ~/paper/figures/fig_MC_scatter_phat_vs_p_FOCs_100000_x.eps: Productivity estimates against true productivities in Monte Carlo simulations (all subfigures (for simulation x=1..5) of Figure D.2 in Supplemental Appendix D)
            --- ~/paper/tables/tab_montecarlo_misspecification_100000_etav2_rho-0.1.tex: Estimation under perfectly negatively group-specific components (Table D.3 in Supplemental Appendix D)
            --- ~/paper/tables/tab_montecarlo_misspecification_100000_etav2_rho0.tex: Estimation under uncorrelated group-specific components (Table D.2 in Supplemental Appendix D)
            --- ~/paper/tables/tab_montecarlo_misspecification_100000_etav2_rho1.tex: Estimation under perfectly positively correlated group-specific components (Table D.4 in Supplemental Appendix D)
            --- ~/paper/tables/tab_counterfactuals_equilibrium_main_text.tex: Effects of eliminating firm heterogeneity in amenities (Table 12 in Section 8 of the main text)
            --- ~/paper/tables/tab_counterfactuals_policies.tex: Effects of simulated equal-pay and equal-hiring policies (Table 13 in Section 8 of the main text)
            --- ~/paper/tables/tab_counterfactuals_equilibrium_appendix.tex: Structural decomposition of the gender pay gap (Table G.1 in Supplemental Appendix G)
            --- ~/paper/tables/tab_cf_policy_equalamenities.tex: Effects of simulated equal amenities policy (Table G.2 in Supplemental Appendix G)
            --- ~/paper/tables/tab_cf_policy_equalhiring_public.tex: Effects of simulated equal hiring policy, restricted to the public sector (Table G.3 in Supplemental Appendix G)
            --- ~/paper/tables/tab_model_fit.tex: Model fit (Table 9 in Section 6 of the main text)
            --- ~/paper/text/txt_model_baseline_eta_v.tex
            --- ~/paper/text/txt_model_baseline_eta_a.tex
            --- ~/paper/text/txt_model_fit_gap_difference.tex
            --- ~/paper/text/txt_model_cf_amenities_gap_decline.tex
            --- ~/paper/text/txt_model_cf_amenities_gap_decline_pp.tex
            --- ~/paper/text/txt_model_cf_amenities_gap_decline_between.tex
            --- ~/paper/text/txt_model_cf_amenities_gap_increase_within.tex
            --- ~/paper/text/txt_model_cf_amenities_employment_increase.tex
            --- ~/paper/text/txt_model_cf_amenities_output_increase.tex
            --- ~/paper/text/txt_model_cf_amenities_workerwelfare_increase.tex
            --- ~/paper/text/txt_model_cf_equalpay_output_decrease.tex
            --- ~/paper/text/txt_model_cf_equalpay_gendergap_closing.tex
            --- ~/paper/text/txt_model_cf_equalhiring_gendergap_decline.tex
            --- ~/paper/text/txt_model_cf_equalamenities_output_decline.tex
            --- ~/paper/text/txt_model_cf_equalamenities_welfare_decline.tex
            --- ~/paper/text/txt_model_cf_equalhiring_public_gendergap_decline.tex
            --- ~/paper/text/txt_model_cf_equalhiring_public_amenitiesgap_increase.tex
            --- ~/paper/text/txt_model_cf_nowedges_output_increase.tex
            --- ~/paper/text/txt_model_cf_nowedges_amenitiesgap_increase.tex
            --- ~/paper/text/txt_model_cf_nowedges_utilitygap_decrease.tex
            --- ~/paper/text/txt_model_cf_utilitygap_baseline.tex
            --- ~/paper/text/txt_model_cf_nowedges_womenwelfare_increase.tex
            --- ~/paper/text/txt_model_cf_frictions_wagegap_decrease.tex
            --- ~/paper/text/txt_model_cf_frictions_utilitygap_decrease.tex
            --- ~/paper/text/txt_model_cf_genderneutral_output_increase.tex
            --- ~/paper/text/txt_model_cf_genderneutral_welfare_increase.tex
      --- MM_19_COMPILE.do: Compiles the paper with all exhibits, including figures, tables, and text snippets, which outputs the following:
            --- ~/paper/MM2025.pdf
      --- MM_AKM_KSS.m: Estimates KSS correction to AKM variance decomposition, which is automatically called by ~/code/data/MM_3_AKM.do
      --- MM_AKM.m: Estimates worker fixed effects, employer fixed effects, time fixed effects, returns to demographics, and additional controls based on Abowd, Kramarz, and Margolis (1999) using the algorithm by Card, Heining, and Kline (2013)
      --- MM_CONNECTED_LOO.m: Finds the largest leave-one-out connected set---i.e., a connected set for which removal of one individual work history at a time leaves the set connected---see Appendix B of Kline, Saggio, and Sølvsten (2020) for details
      --- MM_CONNECTED.m: Finds the (weakly or strongly) connected set of employers
      --- MM_FUN_ADJACENCY.m: Builds the adjacency matrix of a bipartite graph based on worker IDs and employer IDs
      --- MM_FUN_CONNECTED.do: Finds (weakly or strongly) (leave-one-out or regular) connected set of employers
      --- MM_FUN_PROGRAMS.do: Contains programs that are used in the other code files
      --- MM_PAGERANKS.m: Computes PageRanks based on the adjacency or transition matrix

--- All the files are called from Stata codes and generate intermediate output files that are further processed by Stata and model files further down the replication pipeline to produce figures and tables. Running the Master file MM_0_MASTER.do calls all subsequent code files, produces all exhibits (i.e., figures, tables, and text snippets), and compiles the paper in .pdf format.


### ----------------------------------------------------
### REPLICATION CODE FOLDER ~/code/data/_matlab_packages
### ----------------------------------------------------

--- This folder contains all the packages required for the execution of the MATLAB codes in ~/code/data. These packages comprise:
      --- LeaveOutTwoWay-3.02: Leave-out routines from Kline, Saggio, and Sølvsten (2020)
      --- matlab_bgl: Graph algorithms from Gleich (2025)

--- The packages come in compressed .zip format, which are automatically unzipped as part of the third main file (~/code/data/MM_0_MASTER.do).


### ---------------------------------------------------
### REPLICATION CODE FOLDER ~/code/data/_stata_packages
### ---------------------------------------------------

--- This folder contains all the packages required for the execution of the Stata codes in ~/code/data. These packages comprise:
      --- binscatter
      --- confirmdir
      --- egenmore
      --- ftools
      --- gtools
      --- reghdfe


## ------------------------------------
## REPLICATION CODE FOLDER ~/code/model
## ------------------------------------

--- The following two subsubsections describe the contents of the codes used for estimation and solution of the structural model.

--- All codes contained in the subdirectories of the replication code folder ~/code/model are automatically executed from the third main file (~/code/data/MM_0_MASTER.do). The user need not manually run any of the codes in the replication code folder ~/code/model.


### -----------------------------------------------
### REPLICATION CODE FOLDER ~/code/model/estimation
### -----------------------------------------------

--- This folder contains files that are all automatically run from MM_7_FIRM_PARAMETERS.do and MM_13_ANALYSIS_MODEL.do, which themselves are automatically called from MM_0_MASTER.do.

--- The list of included code files (~/code/model/estimation) is as follows:
      --- do_estimation_men.m: script that executes baseline estimation for men
      --- do_estimation_women.m: script that executes baseline estimation for women
      --- do_read_exogenous_parameters.m: script that reads exogenous parameters passed from Stata
      --- do_robustness.m: script that runs all robustness checks
      --- fun_calculate_b.m: function that calculates the flow value of the outside option based on inputs
      --- fun_estimation_heterogeneous_delta.m: function that runs the algorithm for estimation when separation rates are heterogeneous across firms
      --- fun_estimation.m: function that runs the baseline algorithm for estimation
      --- fun_estimation_robustness_men.m: function that executes estimation for men under different assumptions for robustness checks
      --- fun_estimation_robustness_women.m: function that executes estimation for women under different assumptions for robustness checks
      --- fun_import_data.m: function that reads data outputted by Stata and passes it to MATLAB
      --- fun_mycov.m: helper function for fast computation of covariances

--- All the files are called from Stata codes and generate intermediate output files that are further processed by Stata and model files further down the replication pipeline to produce figures and tables, with a few exceptions. To be precise:
      --- ~/code/data/MM_7_FIRM_PARAMETERS.do calls ~/code/model/estimation/estimation_men.m and ~/code/model/estimation/estimation_women.m, which yields the following output:
            --- lab_params_flow_values.txt: a file containing the value of labor market parameters for the text of the paper stored inside the user-specified temporary directory
            --- firm_parameters_merged_matchG_5_p_pi_z.dta: the Stata file with baseline estimates of productivity, amenities and gender wedges, used to produce further tables by other Stata files and as an input for counterfactual simulations stored inside the user-specified temporary directory
            --- ~/paper/tables/tab_economy_wide_parameters_rank5.tex
      --- ~/code/data/MM_13_ANALYSIS_MODEL.do calls ~/code/estimation/do_robustness.m, which yields the following output:
            --- ~/paper/tables/tab_R1_pagerank.tex
            --- ~/paper/tables/tab_R2_hetdelta.tex
            --- ~/paper/tables/tab_R2_eta_a_robustness.tex


### ---------------------------------------------
### REPLICATION CODE FOLDER ~/code/model/solution
### ---------------------------------------------

--- This folder contains files that are all automatically run from MM_18_SIMULATIONS.do, which itself is automatically called from MM_0_MASTER.do.

--- The list of included code files (~/code/model/solution) is as follows:
      --- do_counterfactuals.m: script that runs all counterfactuals
      --- do_simulations.m: script that runs all Monte Carlo simulations and outputs the Monte Carlo tables described above in ~/code/data:
      --- fun_golden_multi_correct.m: function that solves a vector of univariate golden search minimizations
      --- fun_model_GG.m: function that solves the firm's problem in each counterfactual
      --- fun_model_helper.m: function that run a specific model counterfactual as given by fun_model.m
      --- fun_model.m: function that solves all model counterfactuals, calculates statistics and writes the Tables of counterfactuals described above in ~/code/data:
      --- fun_montecarlo_DGP: function that generates Monte Carlo tables for the misspecified model case, called by do_simulations.m
      --- fun_montecarlo_table.m: function that generates Monte Carlo tables, called by do_simulations.m
      --- fun_mycov.m: helper function for fast computation of covariances
      --- fun_simulate_model.m: function that simulates the distribution of firms in each counterfactual
      --- fun_solve_equalamenities.m: function that solves the equilibrium of the model under the equal amenities policy
      --- fun_solve_equalhiring.m: function that solves the equilibrium of the model under the equal hiring policy
      --- fun_solve_equalpay.m: function that solves the equilibrium of the model under the equal pay policy
      --- fun_solve.m: function that solves the equilibrium of the model for constant vacancy cost
      --- fun_solve_system.m: function that solves the equilibrium of the model and finds the vacancy cost that rationalizes observed vacancies

--- All the files are called from the Stata code MM_18_SIMULATIONS.do and directly generate the tables above.


## ----------------------
## INPUTS FOLDER ~/inputs
## ----------------------

--- This folder contains inputs that are necessary for all codes to run and produce output. It has the following folder and file structure:

inputs
  |____cpi
  |      |____IPCA_IPEA_13February2019.xlsx: IPCA from December 1979 to January 2019
  |____fx
  |      |____fx_data.dta: exchange rates from BRL and ARS to USD from 1959 to 2021
  |____ind
  |      |____ind07_5_to_ind95_5_official.dta: official industry crosswalk from 2007 5-digit codes to 1995 5-digit codes
  |      |____ind85_2_to_ind95_5_official.dta: official industry crosswalk from 1985 2-digit codes to 1995 5-digit codes
  |      |____ind95_5_to_ind07_5_official.dta: official industry crosswalk from 1995 5-digit codes to 2007 5-digit codes
  |      |____ind07_5_to_ind85_2_official.dta: official industry crosswalk from 2007 5-digit codes to 1985 2-digit codes
  |____matlab
  |      |____guesses
  |              |____guess_F_policy_equalamenities.mat: the initial guess for equilibrium CDFs to aid convergence of the equal amenities policy
  |              |____guess_F_policy_equalhiring.mat: the initial guess for equilibrium CDFs to aid convergence of the equal hiring policy
  |              |____guess_F_policy_equalhiring_public.mat: the initial guess for equilibrium CDFs to aid convergence of the equal hiring policy applied only to the public sector
  |              |____guess_F_policy_equalpay.mat: the initial guess for equilibrium CDFs to aid convergence of the equal pay policy
  |              |____guess_V_equalhiring.mat: the initial guess for aggregate equilibrium vacancies to aid convergence of the equal hiring policy
  |              |____guess_V_equalhiring_public.mat: the initial guess for equilibrium CDFs to aid convergence of the equal hiring policy applied only to the public sector
  |              |____guess_V_policy_equalamenities.mat: the initial guess for equilibrium CDFs to aid convergence of the equal amenities policy
  |              |____guess_V_policy_equalpay.mat: the initial guess for equilibrium CDFs to aid convergence of the equal pay policy
  |      |____results (this folder, with subdirectories, include all results of simulations; they are re-generated so these are only used if option model_cfs_to_run in MM_0_MASTER.do is set = 1, the option that skips all counterfactuals)
  |              |____policy_function: this folder contains auxiliary policy functions generated by policy simulations
  |                          |_______amenities_endo_policy.mat: the solved endogenous amenities for the equal pay policy
  |                          |_______amenities_endo_policy_equalame.mat: the solved endogenous amenities for the equal amenities policy
  |              |____vacancy_cost_constant: this folder contains counterfactuals in which the cost shifters of vacancy creation are kept constant to the baseline level for both genders
  |                          |_______moments_baseline_amenities_equal_mean_GE.mat: the moments produced by the equal amenities counterfactual simulation
  |                          |_______moments_baseline_equalhiring_GE.mat: the moments produced by the equal hiring policy counterfactual simulation
  |                          |_______moments_baseline_equalhiring_public_GE.mat: the moments produced by the equal hiring policy counterfactual simulation restricted to the public sector
  |                          |_______moments_baseline_equalpay_GE.mat: the moments produced by the equal pay policy counterfactual simulation

  |                          |_______moments_baseline_noz_GE.mat: the moments produced by the counterfactual simulation where gender wedges are set equal to the mean
  |              |____vacancy_cost_reset: this folder contains moments of counterfactuals in which the cost shifters of vacancy creation are calibrated to match the job-finding rate lambda_u for each gender
  |                          |_______moments_baseline_equal_lab_params_GE.mat: the moments produced by the equal labor market parameters counterfactual simulation
  |                          |_______moments_baseline_GE.mat: the moments produced by the baseline simulation
  |                          |_______moments_baseline_nodifference_all_GE.mat: the moments produced by the counterfactual simulation with no gender differences
  |____mw
  |      |____minwage_nominal_IPEA_13February2019.xlsx: federal minimum wage from July 1940 to December 2019
  |____occ
  |      |____occ_bra_to_occ_us.dta: occupation crosswalk from Brazilian CBO codes to US Census codes
  |      |____occ_us_to_skill_tasks_contents.dta: occupational skill and task contents based on US Census occupation codes
  |      |____occ02_6_to_occ94_5_official.dta: official occupation crosswalk from 2002 6-digit codes to 1994 5-digit codes
  |      |____occ94_5_to_occ02_6_official.dta: official occupation crosswalk from 1994 5-digit codes to 2002 6-digit codes
  |____orbis (the replicator must move all but the last among the following files into this folder in order for the replication to run successfully, unless the global macro sim_orbis = 1 in the third main file (~/code/data/MM_0_MASTER.do), in which case only the last file containing a simulated version of the Orbis Historical dataset is used)
  |      |____Key_financials.part01.rar: Orbis Historical firm financials data, part 1 of 7
  |      |____Key_financials.part01.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 1 of 7
  |      |____Key_financials.part02.rar: Orbis Historical firm financials data, part 2 of 7
  |      |____Key_financials.part02.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 2 of 7
  |      |____Key_financials.part03.rar: Orbis Historical firm financials data, part 3 of 7
  |      |____Key_financials.part03.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 3 of 7
  |      |____Key_financials.part04.rar: Orbis Historical firm financials data, part 4 of 7
  |      |____Key_financials.part04.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 4 of 7
  |      |____Key_financials.part05.rar: Orbis Historical firm financials data, part 5 of 7
  |      |____Key_financials.part05.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 5 of 7
  |      |____Key_financials.part06.rar: Orbis Historical firm financials data, part 6 of 7
  |      |____Key_financials.part06.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 6 of 7
  |      |____Key_financials.part07.rar: Orbis Historical firm financials data, part 7 of 7
  |      |____Key_financials.part07.rar.md5: Orbis Historical firm financials data, checksum or digital fingerprint, part 7 of 7
  |      |____bvd_orbis_historical_bra_sim.dta: Simulated version of the Orbis Historical dataset that is used whenever the global macro sim_orbis = 1 in the third main file (~/code/data/MM_0_MASTER.do)
  |____rais (this folder comes empty as part of the replication package and the replicator must move the following subdirectories and files into it in order for the replication to run successfully)
  |      |____1985
  |              |____AC1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Acre in 1985
  |              |____AL1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Alagoas in 1985
  |              |____AM1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Amazonas in 1985
  |              |____AP1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Amapá in 1985
  |              |____BA1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Bahia in 1985
  |              |____CE1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Ceará in 1985
  |              |____DF1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Distrito Federal in 1985
  |              |____ES1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Espírito Santo in 1985
  |              |____GO1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Goiás in 1985
  |              |____IGNORADO1985ID.7z: RAIS linked employer-employee data for unidentified Brazilian states in 1985
  |              |____MA1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Maranhão in 1985
  |              |____MG1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Minas Gerais in 1985
  |              |____MS1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Mato Grosso do Sul in 1985
  |              |____MT1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Mato Grosso in 1985
  |              |____PA1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Pará in 1985
  |              |____PB1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Paraíba in 1985
  |              |____PE1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Pernambuco in 1985
  |              |____PI1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Piauí in 1985
  |              |____PR1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Paraná in 1985
  |              |____RJ1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Rio de Janeiro in 1985
  |              |____RN1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Rio Grande do Norte in 1985
  |              |____RO1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Rondônia in 1985
  |              |____RR1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Roraima in 1985
  |              |____RS1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Rio Grande do Sul in 1985
  |              |____SC1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Santa Catarina in 1985
  |              |____SE1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Sergipe in 1985
  |              |____SP1985ID.7z: RAIS linked employer-employee data for the Brazilian state of Tocantins in 1985
  |      |____1986
  |              |____AC1986ID.7z
  |              |____AL1986ID.7z
  |              |____AM1986ID.7z
  |              |____AP1986ID.7z
  |              |____BA1986ID.7z
  |              |____CE1986ID.7z
  |              |____DF1986ID.7z
  |              |____ES1986ID.7z
  |              |____GO1986ID.7z
  |              |____IGNORADO1986ID.7z
  |              |____MA1986ID.7z
  |              |____MG1986ID.7z
  |              |____MS1986ID.7z
  |              |____MT1986ID.7z
  |              |____PA1986ID.7z
  |              |____PB1986ID.7z
  |              |____PE1986ID.7z
  |              |____PI1986ID.7z
  |              |____PR1986id.7z
  |              |____RJ1986id.7z
  |              |____RN1986ID.7z
  |              |____RO1986ID.7z
  |              |____RR1986ID.7z
  |              |____RS1986ID.7z
  |              |____SC1986ID.7z
  |              |____SE1986ID.7z
  |              |____SP1986ID.7z
  |      |____1987
  |              |____AC1987ID.7z
  |              |____AL1987ID.7z
  |              |____AM1987ID.7z
  |              |____AP1987ID.7z
  |              |____BA1987ID.7z
  |              |____CE1987ID.7z
  |              |____DF1987ID.7z
  |              |____ES1987ID.7z
  |              |____GO1987ID.7z
  |              |____IGNORADO1987id.7z
  |              |____MA1987ID.7z
  |              |____MG1987ID.7z
  |              |____MS1987ID.7z
  |              |____MT1987ID.7z
  |              |____PA1987ID.7z
  |              |____PB1987ID.7z
  |              |____PE1987ID.7z
  |              |____PI1987ID.7z
  |              |____PR1987ID.7z
  |              |____RJ1987ID.7z
  |              |____RN1987ID.7z
  |              |____RO1987ID.7z
  |              |____RR1987ID.7z
  |              |____RS1987ID.7z
  |              |____SC1987ID.7z
  |              |____SE1987ID.7z
  |              |____SP1987ID.7z
  |      |____1988
  |              |____AC1988ID.7z
  |              |____AL1988ID.7z
  |              |____AM1988ID.7z
  |              |____AP1988ID.7z
  |              |____BA1988ID.7z
  |              |____CE1988ID.7z
  |              |____DF1988ID.7z
  |              |____ES1988ID.7z
  |              |____GO1988ID.7z
  |              |____IGNORADO1988id.7z
  |              |____MA1988ID.7z
  |              |____MG1988ID.7z
  |              |____MS1988ID.7z
  |              |____MT1988ID.7z
  |              |____PA1988ID.7z
  |              |____PB1988ID.7z
  |              |____PE1988ID.7z
  |              |____PI1988ID.7z
  |              |____PR1988ID.7z
  |              |____RJ1988ID.7z
  |              |____RN1988id.7z
  |              |____RO1988ID.7z
  |              |____RR1988ID.7z
  |              |____RS1988ID.7z
  |              |____SC1988ID.7z
  |              |____SE1988ID.7z
  |              |____SP1988ID.7z
  |      |____1989
  |              |____AC1989ID.7z
  |              |____AL1989ID.7z
  |              |____AM1989ID.7z
  |              |____AP1989ID.7z
  |              |____BA1989ID.7z
  |              |____CE1989ID.7z
  |              |____DF1989ID.7z
  |              |____ES1989ID.7z
  |              |____GO1989ID.7z
  |              |____IGNORADO1989ID.7z
  |              |____MA1989ID.7z
  |              |____MG1989ID.7z
  |              |____MS1989ID.7z
  |              |____MT1989ID.7z
  |              |____PA1989ID.7z
  |              |____PB1989ID.7z
  |              |____PE1989ID.7z
  |              |____PI1989ID.7z
  |              |____PR1989ID.7z
  |              |____RJ1989ID.7z
  |              |____RN1989ID.7z
  |              |____RO1989ID.7z
  |              |____RR1989ID.7z
  |              |____RS1989ID.7z
  |              |____SC1989ID.7z
  |              |____SE1989ID.7z
  |              |____SP1989ID.7z
  |              |____TO1989ID.7z
  |      |____1990
  |              |____AC1990ID.7z
  |              |____AL1990ID.7z
  |              |____AM1990ID.7z
  |              |____AP1990ID.7z
  |              |____BA1990ID.7z
  |              |____CE1990ID.7z
  |              |____DF1990ID.7z
  |              |____ES1990ID.7z
  |              |____GO1990ID.7z
  |              |____IGNORADO1990ID.7z
  |              |____MA1990ID.7z
  |              |____MG1990ID.7z
  |              |____MS1990ID.7z
  |              |____MT1990ID.7z
  |              |____PA1990ID.7z
  |              |____PB1990ID.7z
  |              |____PE1990ID.7z
  |              |____PI1990ID.7z
  |              |____PR1990ID.7z
  |              |____RJ1990ID.7z
  |              |____RN1990ID.7z
  |              |____RO1990ID.7z
  |              |____RR1990ID.7z
  |              |____RS1990ID.7z
  |              |____SC1990ID.7z
  |              |____SE1990ID.7z
  |              |____SP1990ID.7z
  |              |____TO1990ID.7z
  |      |____1991
  |              |____AC1991ID.7z
  |              |____AL1991ID.7z
  |              |____AM1991ID.7z
  |              |____AP1991ID.7z
  |              |____BA1991ID.7z
  |              |____CE1991ID.7z
  |              |____DF1991ID.7z
  |              |____ES1991ID.7z
  |              |____GO1991ID.7z
  |              |____IGNORADO1991ID.7z
  |              |____MA1991ID.7z
  |              |____MG1991ID.7z
  |              |____MS1991ID.7z
  |              |____MT1991ID.7z
  |              |____PA1991ID.7z
  |              |____PB1991ID.7z
  |              |____PE1991ID.7z
  |              |____PI1991ID.7z
  |              |____PR1991ID.7z
  |              |____RJ1991ID.7z
  |              |____RN1991ID.7z
  |              |____RO1991ID.7z
  |              |____RR1991id.7z
  |              |____RS1991ID.7z
  |              |____SC1991id.7z
  |              |____SE1991ID.7z
  |              |____SP1991ID.7z
  |              |____TO1991id.7z
  |      |____1992
  |              |____AC1992ID.7z
  |              |____AL1992ID.7z
  |              |____AM1992ID.7z
  |              |____AP1992ID.7z
  |              |____BA1992ID.7z
  |              |____CE1992ID.7z
  |              |____DF1992ID.7z
  |              |____ES1992ID.7z
  |              |____GO1992ID.7z
  |              |____IGNORADO1992ID.7z
  |              |____MA1992ID.7z
  |              |____MG1992ID.7z
  |              |____MS1992ID.7z
  |              |____MT1992ID.7z
  |              |____PA1992ID.7z
  |              |____PB1992ID.7z
  |              |____PE1992ID.7z
  |              |____PI1992ID.7z
  |              |____PR1992ID.7z
  |              |____RJ1992ID.7z
  |              |____RN1992ID.7z
  |              |____RO1992ID.7z
  |              |____RR1992ID.7z
  |              |____RS1992ID.7z
  |              |____SC1992ID.7z
  |              |____SE1992ID.7z
  |              |____SP1992ID.7z
  |              |____TO1992ID.7z
  |      |____1993
  |              |____AC1993ID.7z
  |              |____AL1993ID.7z
  |              |____AM1993ID.7z
  |              |____AP1993ID.7z
  |              |____BA1993ID.7z
  |              |____CE1993ID.7z
  |              |____DF1993ID.7z
  |              |____ES1993ID.7z
  |              |____GO1993ID.7z
  |              |____IGNORADO1993ID.7z
  |              |____MA1993ID.7z
  |              |____MG1993ID.7z
  |              |____MS1993ID.7z
  |              |____MT1993ID.7z
  |              |____PA1993ID.7z
  |              |____PB1993ID.7z
  |              |____PE1993ID.7z
  |              |____PI1993ID.7z
  |              |____PR1993ID.7z
  |              |____RJ1993ID.7z
  |              |____RN1993ID.7z
  |              |____RO1993ID.7z
  |              |____RR1993ID.7z
  |              |____RS1993ID.7z
  |              |____SC1993ID.7z
  |              |____SE1993ID.7z
  |              |____SP1993ID.7z
  |              |____TO1993ID.7z
  |      |____1994
  |              |____AC1994ID.7z
  |              |____AL1994ID.7z
  |              |____AM1994ID.7z
  |              |____AP1994ID.7z
  |              |____BA1994ID.7z
  |              |____CE1994ID.7z
  |              |____DF1994ID.7z
  |              |____ES1994ID.7z
  |              |____GO1994ID.7z
  |              |____IGNORADO1994ID.7z
  |              |____MA1994ID.7z
  |              |____MG1994ID.7z
  |              |____MS1994ID.7z
  |              |____MT1994ID.7z
  |              |____PA1994ID.7z
  |              |____PB1994ID.7z
  |              |____PE1994ID.7z
  |              |____PI1994ID.7z
  |              |____PR1994ID.7z
  |              |____RJ1994ID.7z
  |              |____RN1994ID.7z
  |              |____RO1994ID.7z
  |              |____RR1994ID.7z
  |              |____RS1994ID.7z
  |              |____SC1994ID.7z
  |              |____SE1994ID.7z
  |              |____SP1994ID.7z
  |              |____TO1994ID.7z
  |      |____1995
  |              |____AC1995ID.7z
  |              |____AL1995ID.7z
  |              |____AM1995ID.7z
  |              |____AP1995ID.7z
  |              |____BA1995ID.7z
  |              |____CE1995ID.7z
  |              |____DF1995ID.7z
  |              |____ES1995ID.7z
  |              |____GO1995ID.7z
  |              |____IGNORADO1995ID.7z
  |              |____MA1995ID.7z
  |              |____MG1995ID.7z
  |              |____MS1995ID.7z
  |              |____MT1995ID.7z
  |              |____PA1995ID.7z
  |              |____PB1995ID.7z
  |              |____PE1995ID.7z
  |              |____PI1995ID.7z
  |              |____PR1995ID.7z
  |              |____RJ1995ID.7z
  |              |____RN1995ID.7z
  |              |____RO1995ID.7z
  |              |____RR1995ID.7z
  |              |____RS1995ID.7z
  |              |____SC1995ID.7z
  |              |____SE1995ID.7z
  |              |____SP1995ID.7z
  |              |____TO1995ID.7z
  |      |____1996
  |              |____AC1996ID.7z
  |              |____AL1996ID.7z
  |              |____AM1996id.7z
  |              |____AP1996ID.7z
  |              |____BA1996ID.7z
  |              |____CE1996ID.7z
  |              |____DF1996ID.7z
  |              |____ES1996ID.7z
  |              |____GO1996id.7z
  |              |____IGNORADO1996ID.7z
  |              |____MA1996ID.7z
  |              |____MG1996ID.7z
  |              |____MS1996ID.7z
  |              |____MT1996ID.7z
  |              |____PA1996ID.7z
  |              |____PB1996ID.7z
  |              |____PE1996ID.7z
  |              |____PI1996ID.7z
  |              |____PR1996ID.7z
  |              |____RJ1996ID.7z
  |              |____RN1996ID.7z
  |              |____RO1996ID.7z
  |              |____RR1996ID.7z
  |              |____RS1996ID.7z
  |              |____SC1996ID.7z
  |              |____SE1996ID.7z
  |              |____SP1996ID.7z
  |              |____TO1996ID.7z
  |      |____1997
  |              |____AC1997ID.7z
  |              |____AL1997ID.7z
  |              |____AM1997ID.7z
  |              |____AP1997ID.7z
  |              |____BA1997ID.7z
  |              |____CE1997ID.7z
  |              |____DF1997ID.7z
  |              |____ES1997ID.7z
  |              |____GO1997ID.7z
  |              |____IGNORADO1997ID.7z
  |              |____MA1997ID.7z
  |              |____MG1997ID.7z
  |              |____MS1997ID.7z
  |              |____MT1997ID.7z
  |              |____PA1997ID.7z
  |              |____PB1997ID.7z
  |              |____PE1997ID.7z
  |              |____PI1997ID.7z
  |              |____PR1997ID.7z
  |              |____RJ1997ID.7z
  |              |____RN1997ID.7z
  |              |____RO1997ID.7z
  |              |____RR1997ID.7z
  |              |____RS1997ID.7z
  |              |____SC1997ID.7z
  |              |____SE1997ID.7z
  |              |____SP1997ID.7z
  |              |____TO1997ID.7z
  |      |____1998
  |              |____AC1998ID.7z
  |              |____AL1998ID.7z
  |              |____AM1998ID.7z
  |              |____AP1998ID.7z
  |              |____BA1998ID.7z
  |              |____CE1998ID.7z
  |              |____DF1998ID.7z
  |              |____ES1998ID.7z
  |              |____GO1998ID.7z
  |              |____IGNORADO1998ID.7z
  |              |____MA1998ID.7z
  |              |____MG1998ID.7z
  |              |____MS1998ID.7z
  |              |____MT1998ID.7z
  |              |____PA1998ID.7z
  |              |____PB1998ID.7z
  |              |____PE1998ID.7z
  |              |____PI1998ID.7z
  |              |____PR1998ID.7z
  |              |____RJ1998ID.7z
  |              |____RN1998ID.7z
  |              |____RO1998ID.7z
  |              |____RR1998ID.7z
  |              |____RS1998ID.7z
  |              |____SC1998ID.7z
  |              |____SE1998ID.7z
  |              |____SP1998ID.7z
  |              |____TO1998ID.7z
  |      |____1999
  |              |____AC1999ID.7z
  |              |____AL1999ID.7z
  |              |____AM1999ID.7z
  |              |____AP1999ID.7z
  |              |____BA1999ID.7z
  |              |____CE1999ID.7z
  |              |____DF1999ID.7z
  |              |____ES1999ID.7z
  |              |____GO1999ID.7z
  |              |____IGNORADO1999ID.7z
  |              |____MA1999ID.7z
  |              |____MG1999ID.7z
  |              |____MS1999ID.7z
  |              |____MT1999ID.7z
  |              |____PA1999ID.7z
  |              |____PB1999ID.7z
  |              |____PE1999ID.7z
  |              |____PI1999ID.7z
  |              |____PR1999ID.7z
  |              |____RJ1999ID.7z
  |              |____RN1999ID.7z
  |              |____RO1999ID.7z
  |              |____RR1999ID.7z
  |              |____RS1999ID.7z
  |              |____SC1999ID.7z
  |              |____SE1999ID.7z
  |              |____SP1999ID.7z
  |              |____TO1999ID.7z
  |      |____2000
  |              |____AC2000ID.7z
  |              |____AL2000ID.7z
  |              |____AM2000ID.7z
  |              |____AP2000ID.7z
  |              |____BA2000ID.7z
  |              |____CE2000ID.7z
  |              |____DF2000ID.7z
  |              |____ES2000ID.7z
  |              |____GO2000ID.7z
  |              |____MA2000ID.7z
  |              |____MG2000ID.7z
  |              |____MS2000ID.7z
  |              |____MT2000ID.7z
  |              |____PA2000ID.7z
  |              |____PB2000ID.7z
  |              |____PE2000ID.7z
  |              |____PI2000ID.7z
  |              |____PR2000ID.7z
  |              |____RJ2000ID.7z
  |              |____RN2000ID.7z
  |              |____RO2000ID.7z
  |              |____RR2000ID.7z
  |              |____RS2000ID.7z
  |              |____SC2000ID.7z
  |              |____SE2000ID.7z
  |              |____SP2000ID.7z
  |              |____TO2000ID.7z
  |      |____2001
  |              |____AC2001ID.zip
  |              |____AL2001ID.zip
  |              |____AM2001ID.zip
  |              |____AP2001ID.zip
  |              |____BA2001ID.zip
  |              |____CE2001ID.zip
  |              |____DF2001ID.zip
  |              |____ES2001ID.zip
  |              |____GO2001ID.zip
  |              |____MA2001ID.zip
  |              |____MG2001ID.zip
  |              |____MS2001ID.zip
  |              |____MT2001ID.zip
  |              |____PA2001ID.zip
  |              |____PB2001ID.zip
  |              |____PE2001ID.zip
  |              |____PI2001ID.zip
  |              |____PR2001ID.zip
  |              |____RJ2001ID.zip
  |              |____RN2001ID.zip
  |              |____RO2001ID.zip
  |              |____RR2001ID.zip
  |              |____RS2001ID.zip
  |              |____SC2001ID.zip
  |              |____SE2001ID.zip
  |              |____SP2001ID.zip
  |              |____TO2001ID.zip
  |      |____2002
  |              |____AC2002ID.7z
  |              |____AL2002ID.7z
  |              |____AM2002ID.7z
  |              |____AP2002ID.7z
  |              |____BA2002ID.7z
  |              |____CE2002ID.7z
  |              |____DF2002ID.7z
  |              |____ES2002ID.7z
  |              |____GO2002ID.7z
  |              |____MA2002ID.7z
  |              |____MG2002ID.7z
  |              |____MS2002ID.7z
  |              |____MT2002ID.7z
  |              |____PA2002ID.7z
  |              |____PB2002ID.7z
  |              |____PE2002ID.7z
  |              |____PI2002ID.7z
  |              |____PR2002ID.7z
  |              |____RJ2002ID.7z
  |              |____RN2002ID.7z
  |              |____RO2002ID.7z
  |              |____RR2002ID.7z
  |              |____RS2002ID.7z
  |              |____SC2002ID.7z
  |              |____SE2002ID.7z
  |              |____SP2002ID.7z
  |              |____TO2002ID.7z
  |      |____2003
  |              |____Centro_Oeste2003.7z: RAIS linked employer-employee data for Brazil's Central-East region in 2003
  |              |____ES_RJ_MG2003.7z: RAIS linked employer-employee data for the Brazilian states of Espírito Santo, Rio de Janeiro, and Minas Gerais in 2003
  |              |____Nordeste2003.7z: RAIS linked employer-employee data for Brazil's North-East region in 2003
  |              |____Norte2003.7z: RAIS linked employer-employee data for Brazil's Northern region in 2003
  |              |____sp2003.7z: RAIS linked employer-employee data for the Brazilian state of São Paulo in 2003
  |              |____Sul2003.7z: RAIS linked employer-employee data for Brazil's Southern region in 2003
  |      |____2004
  |              |____centro_oeste2004.7z
  |              |____ES_MG_RJ2004.7z
  |              |____nordeste2004.7z
  |              |____Norte2004.7z
  |              |____SP2004.7z
  |              |____sul2004.7z
  |      |____2005
  |              |____centro05.7z
  |              |____nordeste05.7z
  |              |____norte05.7z
  |              |____sp05.7z
  |              |____sp105.7z
  |              |____sudeste05.7z
  |              |____sul05.7z
  |      |____2006
  |              |____centro06.7z
  |              |____nordeste06.7z
  |              |____norte06.7z
  |              |____sp06.7z
  |              |____sp106.7z
  |              |____sudeste06.7z
  |              |____sul06.7z
  |      |____2007
  |              |____centooeste07.7z
  |              |____nordeste07.7z
  |              |____norte07.7z
  |              |____sp07.7z
  |              |____sudeste07.7z
  |              |____sul07.7z
  |      |____2008
  |              |____AC2008ID.7z
  |              |____AL2008ID.7z
  |              |____AM2008ID.7z
  |              |____AP2008ID.7z
  |              |____BA2008ID.7z
  |              |____CE2008ID.7z
  |              |____DF2008ID.7z
  |              |____ES2008ID.7z
  |              |____GO2008ID.7z
  |              |____MA2008ID.7z
  |              |____MG2008ID.7z
  |              |____MS2008ID.7z
  |              |____MT2008ID.7z
  |              |____PA2008ID.7z
  |              |____PB2008ID.7z
  |              |____PE2008ID.7z
  |              |____PI2008ID.7z
  |              |____PR2008ID.7z
  |              |____RJ2008ID.7z
  |              |____RN2008ID.7z
  |              |____RO2008ID.7z
  |              |____RR2008ID.7z
  |              |____RS2008ID.7z
  |              |____SC2008ID.7z
  |              |____SE2008ID.7z
  |              |____SP2008ID.7z
  |              |____TO2008ID.7z
  |      |____2009
  |              |____AC2009ID.7z
  |              |____AL2009ID.7z
  |              |____AM2009ID.7z
  |              |____AP2009ID.7z
  |              |____BA2009ID.7z
  |              |____CE2009ID.7z
  |              |____DF2009ID.7z
  |              |____ES2009ID.7z
  |              |____GO2009ID2.7z
  |              |____MA2009ID.7z
  |              |____MG2009ID.7z
  |              |____MS2009ID.7z
  |              |____MT2009ID.7z
  |              |____PA2009ID.7z
  |              |____PB2009ID.7z
  |              |____PE2009ID.7z
  |              |____PI2009ID.7z
  |              |____PR2009ID.7z
  |              |____RJ2009ID.7z
  |              |____RN2009ID.7z
  |              |____RO2009ID.7z
  |              |____RR2009ID.7z
  |              |____RS2009ID.7z
  |              |____SC2009ID.7z
  |              |____SE2009ID.7z
  |              |____SP2009ID.7z
  |              |____TO2009ID.7z
  |      |____2010
  |              |____AC2010ID.7z
  |              |____AL2010ID.7z
  |              |____AM2010ID.7z
  |              |____AP2010ID.7z
  |              |____BA2010ID.7z
  |              |____CE2010ID.7z
  |              |____DF2010ID.7z
  |              |____ES2010ID.7z
  |              |____GO2010ID.7z
  |              |____MA2010ID.7z
  |              |____MG2010ID.7z
  |              |____MS2010ID.7z
  |              |____MT2010ID.7z
  |              |____PA2010ID.7z
  |              |____PB2010ID.7z
  |              |____PE2010ID.7z
  |              |____PI2010ID.7z
  |              |____PR2010ID.7z
  |              |____RJ2010ID.7z
  |              |____RN2010ID.7z
  |              |____RO2010ID.7z
  |              |____RR2010ID.7z
  |              |____RS2010ID.7z
  |              |____SC2010ID.7z
  |              |____SE2010ID.7z
  |              |____SP2010ID.7z
  |              |____TO2010ID.7z
  |      |____2011
  |              |____AC2011ID.7z
  |              |____AL2011ID.7z
  |              |____AM2011ID.7z
  |              |____AP2011ID.7z
  |              |____BA2011ID.7z
  |              |____CE2011ID.7z
  |              |____DF2011ID.7z
  |              |____ES2011ID.7z
  |              |____GO2011ID.7z
  |              |____MA2011ID.7z
  |              |____MG2011ID.7z
  |              |____MS2011ID.7z
  |              |____MT2011ID.7z
  |              |____PA2011ID.7z
  |              |____PB2011ID.7z
  |              |____PE2011ID.7z
  |              |____PI2011ID.7z
  |              |____PR2011ID.7z
  |              |____RJ2011ID.7z
  |              |____RN2011ID.7z
  |              |____RO2011ID.7z
  |              |____RR2011ID.7z
  |              |____RS2011ID.7z
  |              |____SC2011ID.7z
  |              |____SE2011ID.7z
  |              |____SP2011ID.7z
  |              |____TO2011ID.7z
  |      |____2012
  |              |____AC2012ID.7z
  |              |____AL2012ID.7z
  |              |____AM2012ID.7z
  |              |____AP2012ID.7z
  |              |____BA2012ID.7z
  |              |____CE2012ID.7z
  |              |____DF2012ID.7z
  |              |____ES2012ID.7z
  |              |____GO2012ID.7z
  |              |____MA2012ID.7z
  |              |____MG2012ID.7z
  |              |____MS2012ID.7z
  |              |____MT2012ID.7z
  |              |____PA2012ID.7z
  |              |____PB2012ID.7z
  |              |____PE2012ID.7z
  |              |____PI2012ID.7z
  |              |____PR2012ID.7z
  |              |____RJ2012ID.7z
  |              |____RN2012ID.7z
  |              |____RO2012ID.7z
  |              |____RR2012ID.7z
  |              |____RS2012ID.7z
  |              |____SC2012ID.7z
  |              |____SE2012ID.7z
  |              |____SP2012ID.7z
  |              |____TO2012ID.7z
  |      |____2013
  |              |____AC2013ID.7z
  |              |____AL2013ID.7z
  |              |____AM2013ID.7z
  |              |____AP2013ID.7z
  |              |____BA2013ID.7z
  |              |____CE2013ID.7z
  |              |____DF2013ID.7z
  |              |____ES2013ID.7z
  |              |____GO2013ID.7z
  |              |____MA2013ID.7z
  |              |____MG2013ID.7z
  |              |____MS2013ID.7z
  |              |____MT2013ID.7z
  |              |____PA2013ID.7z
  |              |____PB2013ID.7z
  |              |____PE2013ID.7z
  |              |____PI2013ID.7z
  |              |____PR2013ID.7z
  |              |____RJ2013ID.7z
  |              |____RN2013ID.7z
  |              |____RO2013ID.7z
  |              |____RR2013ID.7z
  |              |____RS2013ID.7z
  |              |____SC2013ID.7z
  |              |____SE2013ID.7z
  |              |____SP2013ID.7z
  |              |____TO2013ID.7z
  |      |____2014
  |              |____AC2014ID.7z
  |              |____AL2014ID.7z
  |              |____AM2014ID.7z
  |              |____AP2014ID.7z
  |              |____BA2014ID.7z
  |              |____CE2014ID.7z
  |              |____DF2014ID.7z
  |              |____ES2014ID.7z
  |              |____GO2014ID.7z
  |              |____MA2014ID.7z
  |              |____MG2014ID.7z
  |              |____MS2014ID.7z
  |              |____MT2014ID.7z
  |              |____PA2014ID.7z
  |              |____PB2014ID.7z
  |              |____PE2014ID.7z
  |              |____PI2014ID.7z
  |              |____PR2014ID.7z
  |              |____RJ2014ID.7z
  |              |____RN2014ID.7z
  |              |____RO2014ID.7z
  |              |____RR2014ID.7z
  |              |____RS2014ID.7z
  |              |____SC2014ID.7z
  |              |____SE2014ID.7z
  |              |____SP2014ID.7z
  |              |____TO2014ID.7z
  |      |____2015
  |              |____AC2015ID.7z
  |              |____AL2015ID.7z
  |              |____AM2015ID.7z
  |              |____AP2015ID.7z
  |              |____BA2015ID.7z
  |              |____CE2015ID.7z
  |              |____DF2015ID.7z
  |              |____ES2015ID.7z
  |              |____GO2015ID.7z
  |              |____MA2015ID.7z
  |              |____MG2015ID.7z
  |              |____MS2015ID.7z
  |              |____MT2015ID.7z
  |              |____PA2015ID.7z
  |              |____PB2015ID.7z
  |              |____PE2015ID.7z
  |              |____PI2015ID.7z
  |              |____PR2015ID.7z
  |              |____RJ2015ID.7z
  |              |____RN2015ID.7z
  |              |____RO2015ID.7z
  |              |____RR2015ID.7z
  |              |____RS2015ID.7z
  |              |____SC2015ID.7z
  |              |____SE2015ID.7z
  |              |____SP2015ID.7z
  |              |____TO2015ID.7z
  |      |____2016
  |              |____AC2016ID.7z
  |              |____AL2016ID.7z
  |              |____AM2016ID.7z
  |              |____AP2016ID.7z
  |              |____BA2016ID.7z
  |              |____CE2016ID.7z
  |              |____DF2016ID.7z
  |              |____ES2016ID.7z
  |              |____GO2016ID.7z
  |              |____MA2016ID.7z
  |              |____MG2016ID.7z
  |              |____MS2016ID.7z
  |              |____MT2016ID.7z
  |              |____PA2016ID.7z
  |              |____PB2016ID.7z
  |              |____PE2016ID.7z
  |              |____PI2016ID.7z
  |              |____PR2016ID.7z
  |              |____RJ2016ID.7z
  |              |____RN2016ID.7z
  |              |____RO2016ID.7z
  |              |____RR2016ID.7z
  |              |____RS2016ID.7z
  |              |____SC2016ID.7z
  |              |____SE2016ID.7z
  |              |____SP2016ID.7z
  |              |____TO2016ID.7z
  |      |____2017
  |              |____AC2017ID.7z
  |              |____AL2017ID.7z
  |              |____AM2017ID.7z
  |              |____AP2017ID.7z
  |              |____BA2017ID.7z
  |              |____CE2017ID.7z
  |              |____DF2017ID.7z
  |              |____ES2017ID.7z
  |              |____GO2017ID.7z
  |              |____MA2017ID.7z
  |              |____MG2017ID.7z
  |              |____MS2017ID.7z
  |              |____MT2017ID.7z
  |              |____PA2017ID.7z
  |              |____PB2017ID.7z
  |              |____PE2017ID.7z
  |              |____PI2017ID.7z
  |              |____PR2017ID.7z
  |              |____RJ2017ID.7z
  |              |____RN2017ID.7z
  |              |____RO2017ID.7z
  |              |____RR2017ID.7z
  |              |____RS2017ID.7z
  |              |____SC2017ID.7z
  |              |____SE2017ID.7z
  |              |____SP2017ID.7z
  |              |____TO2017ID.7z
  |      |____2018
  |              |____RAIS_VINC_ID_CENTRO_OESTE.7z
  |              |____RAIS_VINC_ID_MG_ES_RJ.7z
  |              |____RAIS_VINC_ID_NORDESTE.7z
  |              |____RAIS_VINC_ID_NORTE.7z
  |              |____RAIS_VINC_ID_SP.7z
  |              |____RAIS_VINC_ID_SUL.7z

--- Note that the subfolders ~/inputs/orbis and ~/inputs/rais that come as part of the replication package are both empty because neither the Orbis Historical dataset nor the RAIS dataset can be made publicly available, as described above. The replicator must upload the data files into subfolders as detailed above in order to successfully execute this replication package.


## --------------------
## PAPER FOLDER ~/paper
## --------------------

--- This folder contains the all files underlying the paper by Morchio and Moser (2025), including:
      --- The .tex files that comprise the paper and supplemental appendix of the paper, including the master file (~/paper/MM2025.tex) and all its dependencies (~/paper/0_abstract.tex, ~/paper/1_introduction.tex, ~/paper/2_data.tex, ~/paper/3_gaps.tex, ~/paper/4_model.tex, ~/paper/5_identification.tex, ~/paper/6_estimation.tex, ~/paper/7_structure.tex, ~/paper/8_counterfactuals.tex, ~/paper/9_conclusion.tex, ~/paper/A_appendix_data.tex, ~/paper/B_appendix_gaps.tex, ~/paper/C_appendix_model.tex, ~/paper/D_appendix_identification.tex, ~/paper/E_appendix_estimation.tex, ~/paper/F_appendix_structure.tex, ~/paper/G_appendix_counterfactuals.tex)
      --- Subdirectories containing all exhibits that are input into the paper, including figures (~/paper/figures), tables (~/paper/tables), and text snippets (~/paper/text)
      --- The bibliography file containing all references that appear in the paper (~/paper/MM2025.bib)
      --- A LaTeX class file (~/paper/AEA.cls)
      --- A number of LaTeX style files (~/paper/multicol.sty, ~/paper/setspace.sty)
      --- A number of BibTeX style files (~/paper/aea.bst, ~/paper/aer.bst)
      --- The compiled paper in .pdf format (~/paper/MM2025.pdf)


# ---------------------------
# INSTRUCTIONS TO REPLICATORS
# ---------------------------

--- Before running any codes, manually add the RAIS data to ~/inputs/RAIS and the Orbis Historical data to ~/inputs/orbis, following the folder and file structure outlined above.

--- Edit ~/code/cleaning_rais/RAIS_0_MASTER.do, ~/code/cleaning_orbis/ORBIS_0_MASTER.do to, and ~/code/data/MM_0_MASTER.do to adjust the user-defined paths:
      --- DIR_MAIN and DIR_TEMP in lines 32-33 of ~/code/cleaning_rais/RAIS_0_MASTER.do
      --- DIR_MAIN, DIR_TEMP, and APP_UNRAR in lines 26-28 of ~/code/cleaning_orbis/ORBIS_0_MASTER.do
      --- DIR_MAIN, DIR_TEMP, APP_MATLAB, APP_PDFLATEX, APP_BIBTEX, APP_LATEX, APP_DVIPS, and APP_PS2PDF in lines 46-53 of ~/code/data/MM_0_MASTER.do

--- First, run ~/code/cleaning_rais/RAIS_0_MASTER.do in order to clean the RAIS data.

--- Second, run ~/code/cleaning_orbis/ORBIS_0_MASTER.do in order to clean the Orbis Historical data.

--- Third, run ~/code/data/MM_0_MASTER.do in order to run all analyses and produce all exhibits contained in Morchio and Moser (2025).

--- The final results comprise:
      --- All exhibits that appear in the paper:
            --- Figures stored in ~/paper/figures
            --- Tables stored in ~/paper/tables
            --- Text snippets stored in ~/paper/text
      --- The compiled paper including all exhibits saved as ~/paper/MM2025.pdf
      --- A set of temporary files in the user-specified directory, which can be deleted without consequences


# ---------------------------
# LIST OF TABLES AND PROGRAMS
# ---------------------------

--- Because the analysis relies on confidential and proprietary data, none of the paper's figures, tables, and text snippets can be reproduced with only the public material provided.

--- However, if the replicator adds the confidential RAIS data and the proprietary Orbis Historical data to the replication folder, as described above, then the provided code reproduces:
      --- All numbers provided in text in the paper
      --- All tables and figures in the paper

--- The following list provides the program and line number, where possible, as well as the output file name for each figure and table included in Morchio and Moser (2025), first using the original file name:
      --- Figure 1: produced by ~/code/data/MM_15_FIGURES.do, line number 150 with output file fig_densities_baseline.eps (panel A) and line number 191 with output file fig_within_baseline.eps (panel B)
      --- Figure 2: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 233 with output file fig_fit_pay.eps (panel A) and line number 245 with output file fig_fit_size.eps (panel B)
      --- Figure 3: produced by ~/code/data/MM_15_FIGURES.do, line number 789 with output file fig_ind_ranks_x_w_m.eps (panel A) and line number 789 with output file fig_ind_ranks_x_w_f.eps (panel B)
      --- Figure 4: produced by ~/code/data/MM_15_FIGURES.do, line number 802 with output file fig_ind_ranks_x_a_m.eps (panel A) and line number 802 with output file fig_ind_ranks_x_a_f.eps (panel B)
      --- Figure 5: produced by ~/code/data/MM_15_FIGURES.do, line number 680 with output file fig_wage_dist.eps (panel A) and line number 692 with output file fig_amenity_dist.eps (panel B)
      --- Figure 6: produced by ~/code/data/MM_15_FIGURES.do, line number 1200 with output file fig_comp_ladder_m.eps (panel A) and line number 1200 with output file fig_comp_ladder_f.eps (panel B)
      --- Figure 7: produced by ~/code/data/MM_15_FIGURES.do, line number 850 with output file fig_dist_amenity_shares.eps (panel A) and line number 918 with output file fig_amenity_shares_ranks.eps (panel B)
      --- Figure A.1: produced by ~/code/data/MM_15_FIGURES.do, line number 1232 with output file fig_appendix_exp_act_vs_exp_pot_m.eps (panel A) and line number 1250 with output file fig_appendix_exp_act_vs_exp_pot_f.eps (panel B)
      --- Figure B.1: produced by ~/code/data/MM_15_FIGURES.do, line number 237 with output file fig_appendix_akm_hours.eps
      --- Figure B.2: produced by ~/code/data/MM_15_FIGURES.do, line number 260 with output file fig_appendix_akm_occ.eps
      --- Figure B.3: produced by ~/code/data/MM_15_FIGURES.do, line number 275 with output file fig_appendix_akm_exp_act.eps
      --- Figure B.4: produced by ~/code/data/MM_15_FIGURES.do, line number 290 with output file fig_appendix_akm_xb_tenure.eps
      --- Figure B.5: produced by ~/code/data/MM_15_FIGURES.do, line number 312 with output file fig_appendix_akm_xb_year_m.eps (panel A) and line number 329 with output file fig_appendix_akm_xb_year_f.eps (panel B)
      --- Figure B.6: produced by ~/code/data/MM_15_FIGURES.do, line number 351 with output file fig_appendix_akm_xb_age_m.eps (panel A) and line number 369 with output file fig_appendix_akm_xb_age_f.eps (panel B)
      --- Figure B.7: produced by ~/code/data/MM_15_FIGURES.do, line number 164 with output file fig_appendix_densities_alt_1.eps (panel A), line number 217 with output file fig_appendix_within_alt_2.eps (panel B), line number 178 with output file fig_appendix_densities_alt_2.eps (panel C) and line number 204 with output file fig_appendix_within_alt_1.eps (panel D)
      --- Figure D.1: produced by ~/code/model/solution/fun_montecarlo_table.m, line number 280 with output files fig_MC_scatter_ahat_vs_a_FOCs_100000_1.eps (panel A), fig_MC_scatter_ahat_vs_a_FOCs_100000_2.eps (panel B), fig_MC_scatter_ahat_vs_a_FOCs_100000_3.eps (panel C), fig_MC_scatter_ahat_vs_a_FOCs_100000_4.eps (panel D), fig_MC_scatter_ahat_vs_a_FOCs_100000_5.eps (panel E)
      --- Figure D.2: produced by ~/code/model/solution/fun_montecarlo_table.m, line number 267 with output files fig_MC_scatter_phat_vs_p_FOCs_100000_1.eps (panel A), fig_MC_scatter_phat_vs_p_FOCs_100000_2.eps (panel B), fig_MC_scatter_phat_vs_p_FOCs_100000_3.eps (panel C), fig_MC_scatter_phat_vs_p_FOCs_100000_4.eps (panel D), fig_MC_scatter_phat_vs_p_FOCs_100000_5.eps (panel E)
      --- Figure D.3: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 420 with output file fig_corr_dem_rank_gender_edu_m.eps (panel A), line number 428 with output file fig_corr_dem_rank_gender_edu_f.eps (panel B), line number 420 with output file fig_corr_dem_rank_gender_parent_m.eps (panel C), line number 428 with output file fig_corr_dem_rank_gender_parent_f.eps (panel D), line number 420 with output file fig_corr_dem_rank_gender_yob_m.eps (panel E), line number 428 with output file fig_corr_dem_rank_gender_yob_f.eps (panel F)
      --- Figure E.1: produced by ~/code/data/MM_15_FIGURES.do, line number 400 with output file fig_kdens_ranks.eps
      --- Figure E.2: produced by ~/code/data/MM_15_FIGURES.do, line number 441 with output file fig_recruiting_unw.eps (panel A) and line number 459 with output file fig_recruiting_w.eps (panel B)
      --- Figure E.3: produced by ~/code/data/MM_15_FIGURES.do, line number 503 with output file fig_productivity_unw.eps (panel A) and line number 521 with output file fig_productivity_w.eps (panel B)
      --- Figure E.4: produced by ~/code/data/MM_15_FIGURES.do, line number 560 with output file fig_gender_wedge_unw.eps (panel A) and line number 578 with output file fig_gender_wedge_w.eps (panel B)
      --- Figure E.5: produced by ~/code/data/MM_15_FIGURES.do, line number 624 with output file fig_amenity_cost_shifters_unw.eps (panel A) and line number 642 with output file fig_amenity_cost_shifters_w.eps (panel B)
      --- Figure E.6: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 1334 with output file fig_model_fit_w_size_m.eps (panel A) and line number 1334 with output file fig_model_fit_w_size_f.eps (panel B)
      --- Figure E.7: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 514 with output file compare_pagerank_size_1.eps (panel A), line number 514 with output file compare_pagerank_size_2 (panel B), line number 514 with output file compare_poaching_size_1.eps (panel C), line number 514 with output file compare_poaching_size_2.eps (panel D)
      --- Figure F.1: produced by ~/code/data/MM_15_FIGURES.do, line number 1441 with output file fig_amenities_wedges.eps
      --- Figure F.2: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 1152 with output file fig_public_share_ladder_m.eps (panel A) and line number 1152 with output file fig_public_share_ladder_f.eps (panel B)
      --- Figure F.3: produced by ~/code/data/MM_15_FIGURES.do, line number 992 with output file fig_prod_ranks.eps (panel A) and line number 1031 with output file fig_log_p_f_log_p_m.eps (panel B)
      --- Figure F.4: produced by ~/code/data/MM_15_FIGURES.do, line number 1395 with output file fig_men_to_women_w.eps (panel A), line number 1378 with output file fig_men_to_women_pi.eps (panel B), line number 1361 with output file fig_men_to_women_x.eps (panel C), line number 1322 with output file fig_women_to_men_w.eps (panel D), line number 1305 with output file fig_women_to_men_pi.eps (panel E), line number 1288 with output file fig_women_to_men_x.eps (panel F)
      --- Table 1: produced by ~/code/data/MM_16_TABLES.do, line number 191 with output file tab_sum_stats.tex
      --- Table 2: produced by ~/code/data/MM_16_TABLES.do, line number 413 with output file tab_akm_combined_decomp.tex
      --- Table 3: produced by ~/code/data/MM_16_TABLES.do, line number 608 with output file tab_kob_log_w_short.tex
      --- Table 4: produced by ~/code/data/MM_16_TABLES.do, line number 663 with output file tab_lab_params.tex
      --- Table 5: produced by ~/code/data/MM_14_ANALYSIS_DATA.do, line number 828 with output file tab_reg_productivity.tex -- note: this table will be based on simulated Orbis Historical data whenever the global macro sim_orbis = 1, which will result in numbers different from the published version of this table based on the proprietary Orbis Historical data that is used whenever the global macro sim_orbis = 0 in the third main file (~/code/data/MM_0_MASTER.do)
      --- Table 6: produced by ~/code/data/MM_16_TABLES.do, line number 1519 with output file tab_reg_wedges.tex
      --- Table 7: produced by ~/code/data/MM_16_TABLES.do, line number 1368 with output file tab_reg_amenities.tex
      --- Table 8: produced by ~/code/data/MM_7_FIRM_PARAMETERS.do, line number 479 with output file tab_economy_wide_parameters_rank5.tex
      --- Table 9: produced by ~/code/model/solution/fun_model.m, line number 499 with output file tab_model_fit.tex
      --- Table 10: produced by ~/code/data/MM_16_TABLES.do, line number 1751 with output file tab_var_pay_decomp.tex
      --- Table 11: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x.tex
      --- Table 12: produced by ~/code/model/solution/fun_model.m, line number 194 with output file tab_counterfactuals_equilibrium_main_text.tex
      --- Table 13: produced by ~/code/model/solution/fun_model.m, line number 200 with output file tab_counterfactuals_policies.tex
      --- Table A.1: produced by ~/code/data/MM_16_TABLES.do, line number 856 with output file tab_appendix_a1.tex
      --- Table A.2: produced by ~/code/data/MM_16_TABLES.do, line number 856 with output file tab_appendix_a2.tex
      --- Table A.3: produced by ~/code/data/MM_16_TABLES.do, line number 856 with output file tab_appendix_a3.tex
      --- Table A.4: produced by ~/code/data/MM_16_TABLES.do, line number 952 with output file tab_appendix_a4.tex
      --- Table A.5: produced by ~/code/data/MM_16_TABLES.do, line number 952 with output file tab_appendix_a5.tex
      --- Table B.1: produced by ~/code/data/MM_16_TABLES.do, line number 588 with output file tab_kob_log_w.tex
      --- Table D.1: produced by ~/code/model/solution/fun_montecarlo_table.m, line number 314 with output file tab_montecarlo_100000.tex
      --- Table D.2: produced by ~/code/model/solution/fun_montecarlo_DGP, line number 303 with output file tab_montecarlo_misspecification_100000_etav2_rho0.tex
      --- Table D.3: produced by ~/code/model/solution/fun_montecarlo_DGP, line number 303 with output file tab_montecarlo_misspecification_100000_etav2_rho-1.tex
      --- Table D.4: produced by ~/code/model/solution/fun_montecarlo_DGP, line number 303 with output file tab_montecarlo_misspecification_100000_etav2_rho1.tex
      --- Table E.1: produced by ~/code/data/MM_16_TABLES.do, line number 765 with output file tab_corr_m.tex (panel A), line number 765 with output file tab_corr_f.tex (panel B) and line number 799 with output file tab_corr_cross.tex (panel C)
      --- Table E.2: produced by ~/code/data/MM_16_TABLES.do, line number 1969 with output file tab_ranks.tex
      --- Table E.3: produced by ~/code/data/MM_13_ANALYSIS_MODEL.do, line number 886 with output file tab_R1_pagerank.tex
      --- Table E.4: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_pageranks.tex
      --- Table E.5: produced by ~/code/data/MM_13_ANALYSIS_MODEL.do, line number 783 with output file tab_R2_hetdelta.tex
      --- Table E.6: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_delta.tex
      --- Table E.7: produced by ~/code/data/MM_13_ANALYSIS_MODEL.do, line number 563 with output file tab_R2_eta_a_robustness.tex
      --- Table E.8: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_eta_a_h.tex
      --- Table E.9: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_eta_a_d.tex
      --- Table F.1: produced by ~/code/data/MM_16_TABLES.do, line number 588 with output file tab_kob_log_pi_tilde.tex
      --- Table F.2: produced by ~/code/data/MM_16_TABLES.do, line number 588 with output file tab_kob_log_x.tex
      --- Table F.3: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_pri.tex
      --- Table F.4: produced by ~/code/data/MM_16_TABLES.do, line number 539 with output file tab_kob_log_w_pi_x_pub.tex
      --- Table G.1: produced by ~/code/model/solution/fun_model.m, line number 241 with output file tab_counterfactuals_equilibrium_appendix.tex
      --- Table G.2: produced by ~/code/model/solution/fun_model.m, line number 215 with output file tab_cf_policy_equalamenities.tex
      --- Table G.3: produced by ~/code/model/solution/fun_model.m, line number 224 with output file tab_cf_policy_equalhiring_public.tex

--- Finally, the file ~/code/data/MM_19_COMPILE.do renames all original figure and table files to naturally named and numbered files:
      --- figure1a.eps, figure1b.eps, ..., figureF4f.eps, all stored in ~/paper/figures
      --- table1.tex, table2.tex, ..., tableG3.tex, all stored in ~/paper/tables


# ----------
# REFERENCES
# ----------

--- Abowd, John M., Francis Kramarz, and David N. Margolis, "High Wage Workers and High Wage Firms," Econometrica, 1999, 67(2), 251–333.

--- Card, David, Jörg Heining, and Patrick Kline, "Workplace Heterogeneity and the Rise of West German Wage Inequality," Quarterly Journal of Economics, 2013, 128(3), 967–1015.

--- Engbom, Niklas and Christian Moser, "Earnings Inequality and the Minimum Wage: Evidence from Brazil," American Economic Review, 2022a, 112(12), 3803-3847.

--- Engbom, Niklas and Christian Moser, "Data and Code for: Earnings Inequality and the Minimum Wage: Evidence from Brazil," Nashville, TN: American Economic Association [publisher], 2022b. Ann Arbor, MI: Inter-university Consortium for Political and Social Research [distributor], 2022-11-21, https://doi.org/10.3886/E172122V1.

--- Gleich, David, "MatlabBGL," 2025, accessed from https://www.mathworks.com/matlabcentral/fileexchange/10922-matlabbgl on August 28, 2025.

--- Instituto de Pesquisa Econômica Aplicada, "Índice nacional de preços ao consumidor amplo (IPCA) geral: índice (dez. 1993 = 100) (PRECOS12_IPCA12), 1979-2019," 2019, accessed from https://www.ipeadata.gov.br/ExibeSerie.aspx?stub=1&serid=36482&module=M on February 13, 2019.

--- Instituto de Pesquisa Econômica Aplicada, "Salário mínimo vigente (MTE12_SALMIN12), 1940-2019," 2020, accessed from http://www.ipeadata.gov.br/ExibeSerie.aspx?serid=1739471028 on January 13, 2020.

--- International Monetary Fund, "Exchange Rates (ER)," 2022, accessed from https://data.imf.org/en/datasets/IMF.STA:ER on August 28, 2025.

--- Kline, Patrick, Raffaele Saggio, and Mikkel Sølvsten, "Leave-Out Estimation of Variance Components," Econometrica, 2020, 88(5), 1859–1898.

--- Ministério da Economia, "Relatório Anual de Informações Sociais (RAIS), 1985-2018," 2020, https://www.rais.gov.br/sitio/index.jsf, accessed via an institutional agreement with Columbia University on August 28, 2020.

--- Moody's Analytics, "Orbis Historical," 2025, Moody's Analytics, https://www.moodys.com/web/en/us/capabilities/company-reference-data/orbis.html, accessed via an institutional agreement with Columbia University on August 28, 2025.

--- Morchio, Iacopo and Christian Moser, "The Gender Pay Gap: Micro Sources and Macro Consequences," American Economic Review, 2025, conditionally accepted on June 16, 2025.


# ----------------
# ACKNOWLEDGEMENTS
# ----------------

--- This project builds on the data cleaning routines developed by Engbom and Moser (2022a). The original routines are separately disseminated as Engbom and Moser (2022b) and available from the OpenICPSR repository at https://doi.org/10.3886/E172122V1. Modified versions of these routines are included as part of the current replication package.

--- This project also builds on the ordinary-least-squares estimation routines developed by Card, Heining, and Kline (2013). The original routines are available from the GitHub repository at https://github.com/rsaggio87/LeaveOutTwoWay. Modified versions of these routines are included as part of the current replication package.

--- This project also builds on the leave-one-out estimation routines developed by Kline, Saggio, and Sølvsten (2020). The original routines are available from Patrick Kline's website at https://eml.berkeley.edu/~pkline/papers/code_CHK.zip. Modified versions of these routines are included as part of the current replication package.
