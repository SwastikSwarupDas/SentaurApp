import { styled, Box } from '@mui/material';
import { AppBar, Toolbar } from '@mui/material';
import { useContext } from 'react';
import { AccountContext } from '../context/AccountProvider';
import { emptyChatImage2 } from '../constants/data';

import LoginDialog from "./account/LoginDialog";
import ChatDialog from './chat/ChatDialog';

const Component = styled(Box)`
    height: 100vh;
    background: linear-gradient(to top right, #02db8c, #3b5998, purple, #bd005e);
`

const Header = styled(AppBar)`
    height:125px;
    background-color:rgba(30,40,60,0.6);
    box-shadow: 'none';
`

const LoginHeader = styled(AppBar)`
    height:0px;
    background-color:#141414;
`

const Image = styled('img')(
    {
        transform: 'translate(0px,  0px)',
        width: 1550,
    }
)

const Messenger = () => {

    const { account } = useContext(AccountContext);

    return (
        <Component>
            {
                account ?
                    <>
                        <Header>
                            <Toolbar>

                            </Toolbar>
                        </Header>
                        <ChatDialog />
                    </>
                    :
                    <>
                        <LoginHeader>

                            <Toolbar>
                            </Toolbar>
                        </LoginHeader>
                        <Box>
                            <Image src={emptyChatImage2} alt="EmptyChatImage" />
                        </Box>
                        <LoginDialog />
                    </>
            }
        </Component>
    )
}

export default Messenger;