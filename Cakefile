{print} = require 'util'
{spawn} = require 'child_process'

task 'build', 'Build lib/ from src/', ->
  iced = spawn 'iced', ['-c', '-o', './', 'src']
  iced.stderr.on 'data', (data) ->
    process.stderr.write data.toString()
  iced.stdout.on 'data', (data) ->
    print data.toString()
  iced.on 'exit', (code) ->
    callback?() if code is 0


task 'watch', 'Watch src/ for changes', ->
  coffee = spawn 'iced', ['-w', '-c', '-o', './', 'src']
  coffee.stderr.on 'data', (data) ->
    process.stderr.write data.toString()
  coffee.stdout.on 'data', (data) ->
    print data.toString()
