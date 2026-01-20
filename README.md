# AZ204-validaCPF
criar codigo para validar CPF
require "cpf_cnpj"

CPF.format(number)            # Format CPF (xxx.xxx.xxx-xx)
CPF.valid?(number)            # Check if a CPF is valid
CPF.generate                  # Generate a random CPF number
CPF.generate(true)            # Generate a formatted number

cpf = CPF.new(number)
cpf.formatted                 # Return formatted CPF (xxx.xxx.xxx-xx)
cpf.stripped                  # Return stripped CPF (xxxxxxxxxxx)
cpf.valid?                    # Check if CPF is valid
cpf.number_without_verifier   # Return CPF without verifier digits

CPF.valid?(number, strict: true)

$ cpf --check 532.820.857-96
$ $?
0

$ cpf --check 53282085796
$ $?
0

$ cpf --format 53282085796
532.820.857-96

$ cpf --strip 532.820.857-96
53282085796

$ cpf --generate
417.524.931-17

$ cpf --generate --strip
76001454809

$ echo 76001454809 | cpf -f
760.014.548-09
