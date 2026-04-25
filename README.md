# ParcelService
 - A framework for sending and receiving data from the server.
--[[
@class ParcelService
	@client
	@server
	@usage

		local ParcelService = require(path.to.ParcelService)
		local session = ParcelService.CreateSession("Test")
		local remote = session:CreateParcel("TestRemote")
		remote:ConnectFromClient(function(player, msg)
			print("Got message from client " .. player.Name .. ": " .. msg)
			return "Hello from the server!"
		end)
		
		remote:ConnectFromServer(function(player, msg)
			print("Got message from server " .. player.Name .. ": " .. msg)
		end)
		
		remote:SendToServer("Hello from the client!")
		remote:FireAllClients("Hello from the server!")
		remote:SendToClient(player, "Hello from the server!")
		remote:Destroy()
		session:Destroy()
]]--
