FROM ncbi/blast:2.12.0

WORKDIR /db
VOLUME ["/db"]

ENV DATA_STORE=https://data.legumeinfo.org/Arachis
RUN printf '%s\n' '#!/bin/bash' 'set -o pipefail -o errexit -o nounset; curl ${DATA_STORE}/${1} | gzip -dc | makeblastdb -parse_seqids -hash_index -dbtype ${2} -taxid ${3} -title "${4}" -out $(basename ${1#.f*.gz})' > /usr/local/bin/mkblastdb \
  && chmod +x /usr/local/bin/mkblastdb

RUN mkblastdb cardenasii/genomes/K10017.gnm1.DQ4M/araca.K10017.gnm1.DQ4M.genome_main.fna.gz nucl 51121 'Arachis cardenasii - genome'
RUN mkblastdb duranensis/annotations/V14167.gnm1.ann1.cxSM/aradu.V14167.gnm1.ann1.cxSM.cds.fna.gz nucl 130453 'Arachis duranensis - CDS'
RUN mkblastdb duranensis/annotations/V14167.gnm1.ann1.cxSM/aradu.V14167.gnm1.ann1.cxSM.protein.faa.gz prot 130453 'Arachis duranensis - protein'
RUN mkblastdb duranensis/genomes/V14167.gnm1.SWBf/aradu.V14167.gnm1.SWBf.genome_main.fna.gz nucl 130453 'Arachis duranensis - genome'
RUN mkblastdb hypogaea/annotations/Tifrunner.gnm2.ann1.4K0L/arahy.Tifrunner.gnm2.ann1.4K0L.cds_primary.fna.gz nucl 3818 'Arachis hypogaea - CDS'
RUN mkblastdb hypogaea/annotations/Tifrunner.gnm2.ann1.4K0L/arahy.Tifrunner.gnm2.ann1.4K0L.protein.faa.gz prot 3818 'Arachis hypogaea - protein'
RUN mkblastdb hypogaea/genomes/Tifrunner.gnm2.J5K5/arahy.Tifrunner.gnm2.J5K5.genome_main.fna.gz nucl 3818 'Arachis hypogaea - genome (assembly version 2)'
RUN mkblastdb ipaensis/annotations/K30076.gnm1.ann1.J37m/araip.K30076.gnm1.ann1.J37m.cds.fna.gz nucl 130454 'Arachis ipaensis - CDS'
RUN mkblastdb ipaensis/annotations/K30076.gnm1.ann1.J37m/araip.K30076.gnm1.ann1.J37m.protein.faa.gz prot 130454 'Arachis ipaensis - protein'
RUN mkblastdb ipaensis/genomes/K30076.gnm1.bXJ8/araip.K30076.gnm1.bXJ8.genome_main.fna.gz nucl 130454 'Arachis ipaensis - genome'
